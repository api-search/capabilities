---
categories:
- mcp
- governance
- supply-chain
- security
consumed_apis:
- github
description: Attaches Sigstore-backed signed provenance to each MCP registry entry — reviewer identity, review date, scope, and a hash of the capability YAML at review time. Exposes a verify-mcp-attestation MCP tool so any downstream consumer can verify the chain.
layout: capability
name: Manage GitHub MCP Registry Attest
operations:
- description: Create a signed attestation for an MCP registry entry
  method: POST
  name: create-attestation
  path: /repos/{owner}/{registry-repo}/attestations
- description: Look up attestations by subject digest
  method: GET
  name: list-attestations
  path: /repos/{owner}/{registry-repo}/attestations/{subject_digest}
- description: Verify the full attestation chain for an MCP server
  method: GET
  name: verify-mcp-attestation
  path: /v1/attestations/{server_urn}/verify
- description: Revoke a previously-issued attestation
  method: PATCH
  name: revoke-attestation
  path: /v1/attestations/{attestation_id}
personas:
- pat
- maya
- riley
provider_name: GitHub
provider_slug: github
search_terms:
- mcp
- registry
- attestation
- sigstore
- provenance
- supply-chain
- audit
---

When something goes wrong with an MCP server, the first three questions are always the same. Who reviewed it? On what date? With what scope? This capability replaces tribal knowledge with signed, machine-verifiable answers.

**What it does**

- Consumes the GitHub Attestations API to attach a Sigstore-backed signed provenance record to each MCP registry entry
- Embeds the reviewer identity, the review date, the scope (binary, code, supply chain, runtime), and a hash of the capability YAML at review time
- Exposes the attestation chain as MCP — a downstream consumer can call `verify-mcp-attestation` and get back a structured "yes / no / why" answer instead of a hand-written summary
- Rotates trust as the org's identity provider rotates — the attestation chain is bound to the IdP, not to the reviewer's personal GitHub account

**Pattern, not invention**

GitHub's artifact attestations exist for npm, container images, and Actions workflows. This capability applies the same pattern to MCP registry entries — because an MCP server gets the same blast radius as any of those, and deserves the same provenance discipline.

**Operational behavior**

- A developer's IDE refuses to install an MCP server whose attestation chain has been revoked or expired
- A downstream consumer of a published MCP server can verify in their own pipeline that the entry was reviewed by the org's security team, not by someone who left two years ago
- An auditor asks "show me everything an agent could have called between Jan and March" and the attestation log is the answer, not the prelude to a six-week investigation

**Why it matters**

This is the capability that makes the rest of the collection defensible. The mirror controls what is consumed. The publish controls what is shared. The allow-list controls what is visible. The attestation is the proof that any of those decisions can be trusted.

**Companion capabilities**

- [manage-github-mcp-registry-mirror](/capabilities/github/manage-github-mcp-registry-mirror/) — what to attest
- [manage-github-mcp-registry-publish](/capabilities/github/manage-github-mcp-registry-publish/) — sign at publish time
- [manage-github-mcp-registry-allow-list](/capabilities/github/manage-github-mcp-registry-allow-list/) — gate by attestation status
