---
categories:
- mcp
- governance
- security
consumed_apis:
- github
description: Filters the GitHub MCP Registry to entries the org's security team has explicitly approved. Exposes a single MCP `list-approved-servers` tool that gates discovery in the IDE — the picker only ever shows reviewed servers.
layout: capability
name: Manage GitHub MCP Registry Allow-List
operations:
- description: Search the registry across approval-relevant dimensions
  method: GET
  name: search-registry
  path: /search/code
- description: List the org's approval-policy facets
  method: GET
  name: list-approval-facets
  path: /v1/allow-list/facets
- description: Return the approved-only slice as MCP tools
  method: GET
  name: list-approved-servers
  path: /v1/allow-list/servers
- description: Update an entry's allow-list status (approve / revoke)
  method: PATCH
  name: update-allow-list-status
  path: /v1/allow-list/servers/{server_urn}
personas:
- pat
- maya
- riley
provider_name: GitHub
provider_slug: github
search_terms:
- mcp
- registry
- allow-list
- search
- governance
- vs-code
- copilot
- security
---

A registry is a list. An allow-list is a decision. This capability turns the GitHub MCP Registry from the former into the latter, scoped per-org.

**What it does**

- Consumes the GitHub Search API to query the registry across approval-relevant dimensions — vendor reputation, license, last-updated, contributor count, security review status
- Filters the result down to entries the org's security team has explicitly approved
- Exposes a single MCP tool — `list-approved-servers` — that returns only the allow-listed slice
- Runs in the IDE every time a developer opens the MCP picker, so the picker never shows them an unreviewed server

**Structured payload, not a Slack message**

Each entry returned includes the registry URN, the org-policy tags, the security review date, the reviewer, and a pointer to the underlying mirror entry. Coding assistants can reason about it. Humans can read it. The org owns the shape.

**Operational behavior**

- A developer opens VS Code, types `@MCP` in the Copilot palette, sees only the servers their org has reviewed
- A security incident response replaces an entry's allow-list status with `revoked` and the next palette refresh stops surfacing it — no IDE patching required
- A vendor MCP server passes review and gets added to the allow-list, surfaces in the palette within minutes, and the developers most likely to want it find it without an email

**Companion capabilities**

- [manage-github-mcp-registry-mirror](/capabilities/github/manage-github-mcp-registry-mirror/) — the mirror this allow-list filters
- [manage-github-mcp-registry-attest](/capabilities/github/manage-github-mcp-registry-attest/) — the proof behind each approval
- [manage-github-mcp-registry-publish](/capabilities/github/manage-github-mcp-registry-publish/) — outbound publish path
