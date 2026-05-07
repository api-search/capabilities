---
categories: []
consumed_apis: []
description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
layout: capability
name: Agent Md Skill Md Tutorial Capability
operations:
- description: Return AGENTS.md and any SKILL.md files for a repo as combined agent prompt context.
  method: GET
  name: get-agent-context
  path: /agent-context/{{owner}}/{{repo}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- return agents.md and any skill.md files for a repo as combined agent prompt context.
- governance
- spec-driven integration
- get skill md
- api integration
- fetch a skill.md for a named skill in a repo.
- get agent context
- fetch a repo's agents.md.
- skill
- ai
- capabilities
- tutorial
- agents.md
- mcp
- get agents md
- naftiko
slug: agent-md-skill-md-tutorial-capability
source_filename: agent-md-skill-md-tutorial-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Agent Md Skill Md Tutorial Capability\n  description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.\n  tags:\n  - Naftiko\n  - Tutorial\n  - AGENTS.md\n  - Skill\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: github-env\n  description: GitHub token for fetching AGENTS.md and SKILL.md from a repo.\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - namespace: github\n    type: http\n    baseUri: https://api.github.com\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: agents-md\n      path: /repos/{{owner}}/{{repo}}/contents/AGENTS.md\n      operations:\n      - name: get-agents-md\n        method: GET\n        inputParameters:\n        - name: owner\n          in: path\n        - name: repo\n          in: path\n    - name: skill-md\n\
  \      path: /repos/{{owner}}/{{repo}}/contents/.claude/skills/{{skill}}/SKILL.md\n      operations:\n      - name: get-skill-md\n        method: GET\n        inputParameters:\n        - name: owner\n          in: path\n        - name: repo\n          in: path\n        - name: skill\n          in: path\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: agent-md-skill-md-tutorial-capability-rest\n    description: REST surface that returns AGENTS.md + SKILL.md content as a tutorial example.\n    resources:\n    - name: agent-context\n      path: /agent-context/{{owner}}/{{repo}}\n      operations:\n      - method: GET\n        name: get-agent-context\n        description: Return AGENTS.md and any SKILL.md files for a repo as combined agent prompt context.\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n        - name: repo\n          in: path\n          type: string\n        call: github.get-agents-md\n  - type:\
  \ mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: agent-md-skill-md-tutorial-capability-mcp\n    description: MCP server exposing AGENTS.md + SKILL.md retrieval as agent tools.\n    tools:\n    - name: get-agents-md\n      description: Fetch a repo's AGENTS.md.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: owner\n        type: string\n        required: true\n      - name: repo\n        type: string\n        required: true\n      call: github.get-agents-md\n    - name: get-skill-md\n      description: Fetch a SKILL.md for a named skill in a repo.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: owner\n        type: string\n        required: true\n      - name: repo\n        type: string\n        required: true\n      - name: skill\n        type: string\n        required: true\n      call: github.get-skill-md\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: agent-md-skill-md-tutorial-capability-skills\n\
  \    description: Tutorial Skill bundle showing AGENTS.md / SKILL.md retrieval.\n    skills:\n    - name: agent-md-skill-md-tutorial-capability\n      description: Tutorial example reading AGENTS.md and SKILL.md from a repo.\n      location: file:///opt/naftiko/skills/agent-md-skill-md-tutorial-capability\n      allowed-tools: get-agents-md,get-skill-md\n      tools:\n      - name: get-agents-md\n        from:\n          sourceNamespace: agent-md-skill-md-tutorial-capability-mcp\n          action: get-agents-md\n      - name: get-skill-md\n        from:\n          sourceNamespace: agent-md-skill-md-tutorial-capability-mcp\n          action: get-skill-md\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/agent-md-skill-md-tutorial-capability.yaml
tags:
- Naftiko
- Tutorial
- AGENTS.md
- Skill
tools:
- description: Fetch a repo's AGENTS.md.
  hints:
    readOnly: true
  name: get-agents-md
- description: Fetch a SKILL.md for a named skill in a repo.
  hints:
    readOnly: true
  name: get-skill-md
---
