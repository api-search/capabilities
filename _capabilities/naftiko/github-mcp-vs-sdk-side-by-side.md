---
categories: []
consumed_apis: []
description: A comparison capability calling the same GitHub action through GitHub MCP and the Octokit SDK — exposes both surfaces side-by-side for side-by-side eval.
layout: capability
name: Github Mcp Vs Sdk Side By Side
operations:
- description: ''
  method: GET
  name: get-repo-side-by-side
  path: /compare/{{owner}}/{{repo}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- github
- governance
- list issues
- naftiko
- get repo side by side
- mcp vs sdk
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- get repo
slug: github-mcp-vs-sdk-side-by-side
source_filename: github-mcp-vs-sdk-side-by-side.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Github Mcp Vs Sdk Side By Side\n  description: A comparison capability calling the same GitHub action through GitHub MCP and the Octokit SDK — exposes both surfaces side-by-side for side-by-side eval.\n  tags: [Naftiko, GitHub, MCP vs SDK]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: github-env\n  keys: {GITHUB_TOKEN: GITHUB_TOKEN}\ncapability:\n  consumes:\n  - namespace: github\n    type: http\n    baseUri: https://api.github.com\n    authentication: {type: bearer, token: '{{GITHUB_TOKEN}}'}\n    resources:\n    - name: repo\n      path: '/repos/{{owner}}/{{repo}}'\n      operations:\n      - {name: get-repo, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n    - name: issues\n      path: '/repos/{{owner}}/{{repo}}/issues'\n      operations:\n      - {name: list-issues, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n  exposes:\n  - type: rest\n\
  \    address: 0.0.0.0\n    port: 8080\n    namespace: github-mcp-vs-sdk-side-by-side-rest\n    description: REST surface for the MCP-vs-SDK comparison.\n    resources:\n    - {name: repo, path: '/compare/{{owner}}/{{repo}}', operations: [{method: GET, name: get-repo-side-by-side, inputParameters: [{name: owner, in: path, type: string}, {name: repo, in: path, type: string}], call: github.get-repo}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: github-mcp-vs-sdk-side-by-side-mcp\n    description: MCP for the comparison.\n    tools:\n    - name: get-repo\n      hints: {readOnly: true}\n      inputParameters: [{name: owner, type: string, required: true}, {name: repo, type: string, required: true}]\n      call: github.get-repo\n    - name: list-issues\n      hints: {readOnly: true}\n      inputParameters: [{name: owner, type: string, required: true}, {name: repo, type: string, required: true}]\n      call: github.list-issues\n  - type: skill\n    address: 0.0.0.0\n \
  \   port: 3011\n    namespace: github-mcp-vs-sdk-side-by-side-skills\n    description: Skill for the MCP/SDK comparison.\n    skills:\n    - name: github-mcp-vs-sdk-side-by-side\n      description: GitHub MCP vs SDK comparison.\n      location: file:///opt/naftiko/skills/github-mcp-vs-sdk-side-by-side\n      allowed-tools: get-repo,list-issues\n      tools:\n      - {name: get-repo, from: {sourceNamespace: github-mcp-vs-sdk-side-by-side-mcp, action: get-repo}}\n      - {name: list-issues, from: {sourceNamespace: github-mcp-vs-sdk-side-by-side-mcp, action: list-issues}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/github-mcp-vs-sdk-side-by-side.yaml
tags:
- Naftiko
- GitHub
- MCP vs SDK
tools:
- description: ''
  hints:
    readOnly: true
  name: get-repo
- description: ''
  hints:
    readOnly: true
  name: list-issues
---
