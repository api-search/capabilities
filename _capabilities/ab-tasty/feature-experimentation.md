---
consumed_apis:
- decision-api
description: Unified workflow for server-side feature experimentation, A/B testing, and feature flag management. Enables developers and product teams to evaluate campaigns, retrieve flag values, and track activations for controlled rollouts and experiments.
layout: capability
name: AB Tasty Feature Experimentation
operations:
- description: Evaluate visitor context and retrieve all matching campaign assignments
  method: POST
  name: get-campaigns
  path: /v1/campaigns
- description: Get assignment for a specific campaign by ID
  method: POST
  name: get-campaign
  path: /v1/campaigns/{campaignId}
- description: Retrieve feature flag values and metadata for a visitor
  method: POST
  name: get-flags
  path: /v1/flags
- description: Manually activate a campaign variation for a visitor
  method: POST
  name: activate-campaign
  path: /v1/activate
personas: []
provider_name: AB Tasty
provider_slug: ab-tasty
search_terms:
- get assignment for a specific campaign by id
- get campaigns
- manual campaign activation
- retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive rollouts
- get flags
- aggregation
- manually activate a campaign variation for a visitor
- conversion tracking and experiment measurement
- activate campaign
- server side
- experimentation
- a/b testing, multivariate testing, and experiment management
- backend or frontend developer implementing server-side experiments and feature flags
- manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false
- product manager monitoring experiment assignments and flag rollouts
- feature flag evaluation operations
- quality assurance engineer using remote control api to test experiments
- unified workflow for server-side feature experimentation, a/b testing, and feature flag management
- retrieve feature flag values and metadata for a visitor
- progressive feature releases and feature toggles
- Product Manager
- get campaign
- evaluate visitor context and retrieve all matching campaign assignments
- retrieve campaign assignments for a visitor based on context
- a/b testing
- ab tasty
- retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation
- evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side rendering
- activate experiment
- get visitor flags
- Developer
- get visitor campaign
- get visitor campaigns
- feature flags
- retrieve a specific campaign assignment for a visitor
- personalization
slug: feature-experimentation
tags:
- AB Tasty
- Experimentation
- Feature Flags
- A/B Testing
- Server Side
tools:
- description: Evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side rendering
  hints:
    openWorld: false
    readOnly: true
  name: get-visitor-campaigns
- description: Retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation
  hints:
    openWorld: false
    readOnly: true
  name: get-visitor-campaign
- description: Retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive rollouts
  hints:
    openWorld: false
    readOnly: true
  name: get-visitor-flags
- description: Manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activate-experiment
---
