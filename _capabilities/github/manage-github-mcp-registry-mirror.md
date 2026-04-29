---
categories:
- mcp
- governance
- developer-experience
consumed_apis:
- github
description: Pulls approved entries from the GitHub MCP Registry into a governed internal mirror as Naftiko capabilities, attaching org policy and sensitivity tags on the way in. Exposes the mirror as MCP for VS Code and Copilot to install from — only the slice the org has approved is visible.
layout: capability
name: Manage GitHub MCP Registry Mirror
operations:
- description: Read directory tree of registry entries
  method: GET
  name: list-registry-entries
  path: /repos/{owner}/{registry-repo}/contents/{path}
- description: Fetch a single registry-entry manifest
  method: GET
  name: get-registry-entry
  path: /repos/{owner}/{registry-repo}/contents/{path}/{filename}
- description: List approved MCP servers as MCP tools for the IDE
  method: GET
  name: list-mirrored-servers
  path: /v1/mirrored-servers
personas:
- pat
- maya
- riley
provider_name: GitHub
provider_slug: github
search_terms:
- mcp
- registry
- mirror
- governance
- allow-list
- vs-code
- copilot
---

Pulls approved entries from the GitHub MCP Registry into a governed internal mirror as Naftiko capabilities, attaching org policy and sensitivity tags on the way in.

The pattern is straightforward and proven — Schneider Electric has been running the same shape against the open-source community three-URL registry for months. This capability ports that shape onto GitHub's official registry without losing the governance gates.

**What it does**

- Consumes the GitHub Contents API to read every entry in the GitHub MCP Registry repo (or a configured subset)
- Runs each entry through the org's Spectral ruleset and Kyverno gates before it lands in the internal mirror
- Tags every mirrored entry with data-sensitivity, vendor-risk, and security-review metadata
- Exposes the mirror as MCP tools that VS Code and Copilot install from — no sidebar tutorials, no "ask security first" Slack threads

**Why it matters**

The mirror is the safest first capability to ship in the GitHub MCP Registry management collection. It does not require publish access, does not change anything in the public registry, and gives the org a clean kill-switch — flip an entry off in the mirror and the IDE pulls a fresh list on the next refresh.

**Companion capabilities**

- [manage-github-mcp-registry-publish](/capabilities/github/manage-github-mcp-registry-publish/) — publish capability YAMLs back into the registry as PRs
- [manage-github-mcp-registry-allow-list](/capabilities/github/manage-github-mcp-registry-allow-list/) — filter the mirror to a per-org allow-list
- [manage-github-mcp-registry-attest](/capabilities/github/manage-github-mcp-registry-attest/) — sign each mirrored entry with provenance
