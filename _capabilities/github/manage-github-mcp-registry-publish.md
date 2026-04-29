---
categories:
- mcp
- governance
- developer-experience
consumed_apis:
- github
description: Takes a Naftiko capability YAML, packages it into a registry-shaped manifest, and opens a pull request against the GitHub MCP Registry — with the org's governance metadata baked into the entry. Stops at the PR; review and merge stay in GitHub.
layout: capability
name: Manage GitHub MCP Registry Publish
operations:
- description: Create a branch on the registry fork
  method: POST
  name: create-branch
  path: /repos/{fork-owner}/{registry-repo}/git/refs
- description: Write the registry-shaped manifest
  method: PUT
  name: commit-manifest
  path: /repos/{fork-owner}/{registry-repo}/contents/{path}
- description: Open a pull request against the public registry
  method: POST
  name: open-pull-request
  path: /repos/{owner}/{registry-repo}/pulls
- description: Build a registry manifest from a Naftiko capability YAML
  method: POST
  name: build-registry-manifest
  path: /v1/capabilities/{slug}/manifest
personas:
- pat
- maya
- riley
provider_name: GitHub
provider_slug: github
search_terms:
- mcp
- registry
- publish
- pull-request
- governance
- naftiko
---

Takes a Naftiko capability YAML, packages it into a GitHub-MCP-Registry-shaped manifest, and opens a pull request against the public registry — with the org's governance metadata baked into the entry so a downstream consumer can see what was actually reviewed.

**What it does**

- Consumes the GitHub Contents API to write the manifest into a new branch on a fork of the registry
- Consumes the GitHub Pulls API to open the PR with a description that links back to the originating capability YAML
- Embeds tags-on-consumes, tags-on-exposed-operations, and the governance ruleset directly into the registry entry's metadata
- Stops at the PR — review and merge stay in GitHub, where the org's security and platform teams already work

**Design choice: PR over direct write**

The capability does not auto-merge. It does not skip review. It does not request direct-push access on the public registry repo (which nobody wants to grant). It just turns a capability YAML into a governance-rich PR that the GitHub-native review flow can handle.

**Why it matters**

If the org is running an internal MCP server today and has not yet decided whether to publish it externally, this is the capability that lets them publish on their terms — with the same audit trail as any internal API change.

**Companion capabilities**

- [manage-github-mcp-registry-mirror](/capabilities/github/manage-github-mcp-registry-mirror/) — pull approved entries inbound
- [manage-github-mcp-registry-allow-list](/capabilities/github/manage-github-mcp-registry-allow-list/) — filter what's visible to the IDE
- [manage-github-mcp-registry-attest](/capabilities/github/manage-github-mcp-registry-attest/) — sign published entries with provenance
