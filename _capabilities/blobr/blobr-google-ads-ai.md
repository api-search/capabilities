---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Blobr Google Ads Ai
operations: []
personas: []
provider_name: Blobr
provider_slug: blobr
search_terms:
- ai agents
- advertising
- ppc
- google ads
- marketing automation
slug: blobr-google-ads-ai
source_yaml: "name: Blobr Google Ads AI Platform Capability\ndescription: >-\n  Naftiko capability definition for Blobr's AI-powered Google Ads management platform,\n  providing campaign analysis, AI recommendations, and automated optimization via\n  50+ specialized AI agents.\nversion: 1.0.0\ncapabilities:\n  - name: connectAccount\n    description: Connect a Google Ads account to Blobr for AI analysis and management\n    method: POST\n    path: /accounts/connect\n    body:\n      googleAdsCustomerId: string\n  - name: listAccounts\n    description: List all Google Ads accounts connected to Blobr\n    method: GET\n    path: /accounts\n  - name: listCampaigns\n    description: List campaigns for a connected Google Ads account with performance metrics\n    method: GET\n    path: /accounts/{accountId}/campaigns\n  - name: listRecommendations\n    description: List AI-generated recommendations pending review\n    method: GET\n    path: /accounts/{accountId}/recommendations\n    parameters:\n\
  \      - name: status\n        type: string\n        required: false\n        description: Filter by status (pending, approved, rejected, applied)\n      - name: agentType\n        type: string\n        required: false\n      - name: priority\n        type: string\n        required: false\n  - name: approveRecommendation\n    description: Approve an AI recommendation for application to Google Ads\n    method: POST\n    path: /recommendations/{recommendationId}/approve\n  - name: rejectRecommendation\n    description: Reject an AI recommendation\n    method: POST\n    path: /recommendations/{recommendationId}/reject\n  - name: bulkApprove\n    description: Approve multiple recommendations at once\n    method: POST\n    path: /accounts/{accountId}/recommendations/bulk-approve\n  - name: runAgentNow\n    description: Trigger an AI agent to run immediately outside of scheduled cycle\n    method: POST\n    path: /accounts/{accountId}/agents/{agentType}/run\n  - name: configureRules\n    description:\
  \ Set custom rules and constraints governing AI agent behavior\n    method: PUT\n    path: /accounts/{accountId}/rules\nauthentication:\n  type: oauth2\n  flows:\n    authorizationCode:\n      authorizationUrl: https://app.blobr.ai/oauth/authorize\n      tokenUrl: https://app.blobr.ai/oauth/token\n      scopes:\n        accounts:read: Read connected account data\n        recommendations:read: Read AI recommendations\n        recommendations:write: Approve or reject recommendations\n        agents:execute: Trigger agent runs\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blobr/refs/heads/main/capabilities/blobr-google-ads-ai.yaml
tags: []
tools: []
---
