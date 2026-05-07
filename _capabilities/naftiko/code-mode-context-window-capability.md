---
categories: []
consumed_apis: []
description: A capability that packs IDE-relevant context (open files, recent diffs, related symbols) into a token-budgeted code-mode context window.
layout: capability
name: Code Mode Context Window Capability
operations:
- description: ''
  method: GET
  name: get-code-context
  path: /context/{{owner}}/{{repo}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- get code context
- context
- ai
- ide
- capabilities
- api integration
- mcp
- naftiko
slug: code-mode-context-window-capability
source_filename: code-mode-context-window-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Code Mode Context Window Capability\n  description: A capability that packs IDE-relevant context (open files, recent diffs, related symbols) into a token-budgeted code-mode context window.\n  tags: [Naftiko, IDE, Context]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: github-env\n  keys: {GITHUB_TOKEN: GITHUB_TOKEN}\ncapability:\n  consumes:\n  - namespace: github\n    type: http\n    baseUri: https://api.github.com\n    authentication: {type: bearer, token: '{{GITHUB_TOKEN}}'}\n    resources:\n    - name: contents\n      path: /repos/{{owner}}/{{repo}}/contents/{{path}}\n      operations:\n      - {name: get-file, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}, {name: path, in: path}]}\n    - name: pulls\n      path: /repos/{{owner}}/{{repo}}/pulls\n      operations:\n      - {name: list-pulls, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n \
  \   - name: pull-files\n      path: /repos/{{owner}}/{{repo}}/pulls/{{pull_number}}/files\n      operations:\n      - {name: list-pull-files, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}, {name: pull_number, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: code-mode-context-window-capability-rest\n    description: REST surface that builds a code-mode context window for an IDE prompt.\n    resources:\n    - name: context\n      path: /context/{{owner}}/{{repo}}\n      operations:\n      - {method: GET, name: get-code-context, inputParameters: [{name: owner, in: path, type: string}, {name: repo, in: path, type: string}], call: github.get-file}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: code-mode-context-window-capability-mcp\n    description: MCP for building IDE context windows.\n    tools:\n    - name: get-code-context\n      hints: {readOnly: true}\n      inputParameters: [{name: owner,\
  \ type: string, required: true}, {name: repo, type: string, required: true}]\n      call: github.get-file\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: code-mode-context-window-capability-skills\n    description: Skill for code-mode context.\n    skills:\n    - name: code-mode-context-window-capability\n      description: Token-budgeted code-mode context window.\n      location: file:///opt/naftiko/skills/code-mode-context-window-capability\n      allowed-tools: get-code-context\n      tools:\n      - {name: get-code-context, from: {sourceNamespace: code-mode-context-window-capability-mcp, action: get-code-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/code-mode-context-window-capability.yaml
tags:
- Naftiko
- IDE
- Context
tools:
- description: ''
  hints:
    readOnly: true
  name: get-code-context
---
