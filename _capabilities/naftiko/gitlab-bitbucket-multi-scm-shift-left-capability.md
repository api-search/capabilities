---
categories: []
consumed_apis: []
description: A capability that runs governance checks across GitLab + Bitbucket repos for orgs with multi-SCM estate, normalizing results into a single feed.
layout: capability
name: Gitlab Bitbucket Multi Scm Shift Left Capability
operations:
- description: ''
  method: GET
  name: get-multi-scm-feed
  path: /review-feed
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- get multi scm feed
- list merge requests
- multi-scm
- list bitbucket prs
- mcp
- gitlab
- capabilities
- naftiko
- bitbucket
- api integration
- governance
- ai
- list gitlab projects
slug: gitlab-bitbucket-multi-scm-shift-left-capability
source_filename: gitlab-bitbucket-multi-scm-shift-left-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Gitlab Bitbucket Multi Scm Shift Left Capability\n  description: A capability that runs governance checks across GitLab + Bitbucket repos for orgs with multi-SCM estate, normalizing results into a single feed.\n  tags: [Naftiko, GitLab, Bitbucket, Multi-SCM]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: gitlab-env\n  keys: {GITLAB_HOST: GITLAB_HOST, GITLAB_TOKEN: GITLAB_TOKEN}\n- namespace: bitbucket-env\n  keys: {BITBUCKET_TOKEN: BITBUCKET_TOKEN}\ncapability:\n  consumes:\n  - namespace: gitlab\n    type: http\n    baseUri: https://{{GITLAB_HOST}}\n    authentication: {type: bearer, token: '{{GITLAB_TOKEN}}'}\n    resources:\n    - {name: projects, path: /api/v4/projects, operations: [{name: list-gitlab-projects, method: GET}]}\n    - name: project-mr\n      path: /api/v4/projects/{{project_id}}/merge_requests\n      operations:\n      - {name: list-merge-requests, method: GET, inputParameters: [{name: project_id,\
  \ in: path}]}\n  - namespace: bitbucket\n    type: http\n    baseUri: https://api.bitbucket.org\n    authentication: {type: bearer, token: '{{BITBUCKET_TOKEN}}'}\n    resources:\n    - name: pull-requests\n      path: /2.0/repositories/{{workspace}}/{{repo}}/pullrequests\n      operations:\n      - {name: list-bitbucket-prs, method: GET, inputParameters: [{name: workspace, in: path}, {name: repo, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: gitlab-bitbucket-multi-scm-shift-left-capability-rest\n    description: REST surface unifying GitLab + Bitbucket review feeds.\n    resources:\n    - {name: review-feed, path: /review-feed, operations: [{method: GET, name: get-multi-scm-feed, call: gitlab.list-merge-requests}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp\n    description: MCP for multi-SCM shift-left.\n    tools:\n    - {name: list-gitlab-projects, hints: {readOnly:\
  \ true}, call: gitlab.list-gitlab-projects}\n    - name: list-merge-requests\n      hints: {readOnly: true}\n      inputParameters: [{name: project_id, type: string, required: true}]\n      call: gitlab.list-merge-requests\n    - name: list-bitbucket-prs\n      hints: {readOnly: true}\n      inputParameters: [{name: workspace, type: string, required: true}, {name: repo, type: string, required: true}]\n      call: bitbucket.list-bitbucket-prs\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: gitlab-bitbucket-multi-scm-shift-left-capability-skills\n    description: Skill for multi-SCM shift-left.\n    skills:\n    - name: gitlab-bitbucket-multi-scm-shift-left-capability\n      description: Multi-SCM shift-left governance.\n      location: file:///opt/naftiko/skills/gitlab-bitbucket-multi-scm-shift-left-capability\n      allowed-tools: list-gitlab-projects,list-merge-requests,list-bitbucket-prs\n      tools:\n      - {name: list-gitlab-projects, from: {sourceNamespace:\
  \ gitlab-bitbucket-multi-scm-shift-left-capability-mcp, action: list-gitlab-projects}}\n      - {name: list-merge-requests, from: {sourceNamespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp, action: list-merge-requests}}\n      - {name: list-bitbucket-prs, from: {sourceNamespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp, action: list-bitbucket-prs}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/gitlab-bitbucket-multi-scm-shift-left-capability.yaml
tags:
- Naftiko
- GitLab
- Bitbucket
- Multi-SCM
tools:
- description: ''
  hints:
    readOnly: true
  name: list-gitlab-projects
- description: ''
  hints:
    readOnly: true
  name: list-merge-requests
- description: ''
  hints:
    readOnly: true
  name: list-bitbucket-prs
---
