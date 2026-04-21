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
- quality assurance engineer using remote control api to test experiments
- Product Manager
- get visitor flags
- retrieve feature flag values and metadata for a visitor
- conversion tracking and experiment measurement
- ab tasty
- aggregation
- feature flags
- retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation
- feature flag evaluation operations
- manual campaign activation
- get visitor campaigns
- retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive rollouts
- get campaigns
- evaluate visitor context and retrieve all matching campaign assignments
- get flags
- unified workflow for server-side feature experimentation, a/b testing, and feature flag management
- experimentation
- activate campaign
- server side
- retrieve a specific campaign assignment for a visitor
- personalization
- get visitor campaign
- a/b testing, multivariate testing, and experiment management
- evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side rendering
- manually activate a campaign variation for a visitor
- manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false
- activate experiment
- a/b testing
- Developer
- get assignment for a specific campaign by id
- get campaign
- backend or frontend developer implementing server-side experiments and feature flags
- progressive feature releases and feature toggles
- product manager monitoring experiment assignments and flag rollouts
- retrieve campaign assignments for a visitor based on context
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
