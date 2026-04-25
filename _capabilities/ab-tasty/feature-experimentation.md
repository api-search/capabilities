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
- get campaigns
- manually activate a campaign variation for a visitor
- get visitor flags
- ab tasty
- a/b testing, multivariate testing, and experiment management
- personalization
- activate campaign
- retrieve a specific campaign assignment for a visitor
- get assignment for a specific campaign by id
- conversion tracking and experiment measurement
- a/b testing
- quality assurance engineer using remote control api to test experiments
- get campaign
- retrieve campaign assignments for a visitor based on context
- backend or frontend developer implementing server-side experiments and feature flags
- feature flag evaluation operations
- feature flags
- unified workflow for server-side feature experimentation, a/b testing, and feature flag management
- server side
- evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side rendering
- evaluate visitor context and retrieve all matching campaign assignments
- get flags
- get visitor campaign
- activate experiment
- product manager monitoring experiment assignments and flag rollouts
- get visitor campaigns
- retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive rollouts
- retrieve feature flag values and metadata for a visitor
- retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation
- Developer
- experimentation
- manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false
- aggregation
- Product Manager
- progressive feature releases and feature toggles
- manual campaign activation
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
