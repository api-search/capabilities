---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability that crawls every place a Chase OpenAPI spec might live — GitHub Search across Chase orgs/repos, plus AWS API Gateway — and exposes the unified result as REST + MCP + Agent Skills so any developer or agent can discover specs across the whole estate from one tool call.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Openapi Spec Aggregation Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- that
- crawls
- every
- place
slug: jpmc-openapi-spec-aggregation-capability
source_filename: jpmc-openapi-spec-aggregation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: "1.0.0-alpha2"

  info:
    title: JPMC OpenAPI Spec Aggregation
    description: >-
      Crawls every place a Chase OpenAPI spec might live — GitHub Search across
      Chase orgs/repos, plus AWS API Gateway — and exposes the unified result
      as REST + MCP + Agent Skills so any developer or agent can discover specs
      across the whole estate from one tool call.
    tags:
      - JPMorgan Chase
      - OpenAPI
      - GitHub
      - AWS API Gateway
      - Discovery
    created: "2026-04-30"
    modified: "2026-04-30"

  binds:
    - namespace: github-env
      description: "GitHub token for searching Chase orgs/repos."
      keys:
        GITHUB_TOKEN: GITHUB_TOKEN
    - namespace: aws-env
      description: "AWS credentials with API Gateway describe/export permissions."
      keys:
        AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID
        AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY
        AWS_REGION: AWS_REGION

  capability:
    consumes:
      - namespace: github
        type: http
        baseUri: "https://api.github.com"
        authentication:
          type: bearer
          token: "{{GITHUB_TOKEN}}"
        resources:
          - name: search-code
            path: "/search/code"
            operations:
              - name: search-openapi-specs
                method: GET
                inputParameters:
                  - name: q
                    in: query
                    description: "Code-search query (e.g. 'org:jpmorganchase filename:openapi.yaml')."

      - namespace: apigateway
        type: http
        baseUri: "https://apigateway.{{AWS_REGION}}.amazonaws.com"
        authentication:
          type: aws-sig-v4
          accessKeyId: "{{AWS_ACCESS_KEY_ID}}"
          secretKey: "{{AWS_SECRET_ACCESS_KEY}}"
          region: "{{AWS_REGION}}"
          service: apigateway
        resources:
          - name: rest-apis
            path: "/restapis"
            operations:
              - name: list-rest-apis
                method: GET
          - name: rest-api-export
            path: "/restapis/{{rest_api_id}}/stages/{{stage_name}}/exports/oas30"
            operations:
              - name: export-rest-api
                method: GET
                inputParameters:
                  - name: rest_api_id
                    in: path
                  - name: stage_name
                    in: path

    exposes:
      - type: rest
        address: "0.0.0.0"
        port: 8080
        namespace: spec-aggregation-rest
        description: REST API for discovering Chase OpenAPI specs across GitHub and AWS API Gateway.
        resources:
          - name: specs
            path: "/find-specs"
            operations:
              - method: GET
                name: find-specs
                description: Find Chase OpenAPI specs by org, source, or query.
                inputParameters:
                  - name: org
                    in: query
                    type: string
                    description: "GitHub org or AWS account scope. Default: jpmorganchase."
                  - name: source
                    in: query
                    type: string
                    description: "Filter to one source: github, gateway, or both. Default: both."
                  - name: query
                    in: query
                    type: string
                    description: "Free-text filter applied to spec metadata."

      - type: mcp
        address: "0.0.0.0"
        port: 3010
        namespace: spec-aggregation-mcp
        description: MCP server for AI agents to discover Chase OpenAPI specs in one call.
        tools:
          - name: find-specs
            description: "Discover Chase OpenAPI specs across GitHub orgs/repos and AWS API Gateway. Returns spec_url, source, repo, last_updated, and gateway_registered for each match."
            hints:
              readOnly: true
            inputParameters:
              - name: org
                type: string
                required: false
                description: "GitHub org or AWS account scope. Default: jpmorganchase."
              - name: source
                type: string
                required: false
                description: "Filter to one source: github, gateway, or both."
              - name: query
                type: string
                required: false

      - type: skill
        address: "0.0.0.0"
        port: 3011
        namespace: spec-aggregation-skills
        description: Agent Skill bundle for installing the find-specs tool into Claude Code or other agents.
        skills:
          - name: chase-spec-discovery
            description: "Discover Chase OpenAPI specs across the whole estate."
            location: "file:///opt/naftiko/skills/chase-spec-discovery"
            allowed-tools: "find-specs"
            argument-hint: "Use to find OpenAPI specs in JPMC GitHub or API Gateway."
            tools:
              - name: find-specs
                description: "Find Chase OpenAPI specs by org, source, or query."
                from:
                  sourceNamespace: spec-aggregation-mcp
                  action: find-specs
---

A capability that crawls every place a Chase OpenAPI spec might live — GitHub Search across Chase orgs/repos, plus AWS API Gateway — and exposes the unified result as REST + MCP + Agent Skills so any developer or agent can discover specs across the whole estate from one tool call. His verbatim ask was "Pulling OpenAPIs from GitHub repos and AWS API Gateway" — this is the single capability that unifies both sources behind one discovery interface, callable from any surface his developers reach for (REST tool, IDE-attached MCP, or installed Skill).
