---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Autonomous Racing Operations
operations: []
personas: []
provider_name: Amazon DeepRacer
provider_slug: amazon-deepracer
search_terms:
- reinforcement learning
- aws
- autonomous vehicles
- machine learning
- robotics
slug: autonomous-racing-operations
source_filename: autonomous-racing-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-deepracer/capabilities/autonomous-racing-operations.yaml\nname: Autonomous Racing Operations\ndescription: Workflow-oriented Naftiko capability for autonomous racing management using Amazon DeepRacer, covering model deployment, leaderboard participation, vehicle configuration, and competitive racing for ML practitioners and racing enthusiasts.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - Machine Learning\n  - Reinforcement Learning\n  - Autonomous Racing\n  - Robotics\n  - AWS\n\nimports:\n  - url: capabilities/shared/deepracer.yaml\n    as: deepracer\n\npersonas:\n  - name: ML Practitioner\n    description: Developer training and iterating on reinforcement learning models for autonomous racing\n  - name: Race Participant\n    description: Competitor submitting models to DeepRacer leaderboards and virtual racing events\n  - name: Event Organizer\n    description: Administrator managing DeepRacer racing\
  \ events, leaderboards, and participant access\n\nworkflows:\n  - name: Evaluate Model Performance\n    description: Review trained reinforcement learning models and their performance metrics before leaderboard submission\n    steps:\n      - step: listModels\n        capability: deepracer\n        description: List all available trained models\n      - step: getModel\n        capability: deepracer\n        description: Inspect model details and training status\n      - step: listTracks\n        capability: deepracer\n        description: Review available tracks for evaluation\n    persona: ML Practitioner\n\n  - name: Participate in Leaderboard\n    description: Find an active leaderboard, review current rankings, and monitor submission performance\n    steps:\n      - step: listLeaderboards\n        capability: deepracer\n        description: List available leaderboards and their submission deadlines\n      - step: getLeaderboard\n        capability: deepracer\n        description: Review\
  \ leaderboard details and track requirements\n      - step: listLeaderboardSubmissions\n        capability: deepracer\n        description: Check current rankings and competitive landscape\n    persona: Race Participant\n\n  - name: Manage Racing Fleet\n    description: Register, configure, and maintain DeepRacer physical vehicles for an organization or event\n    steps:\n      - step: listCars\n        capability: deepracer\n        description: List all registered DeepRacer vehicles\n      - step: getCar\n        capability: deepracer\n        description: Review vehicle configuration and assignment\n      - step: updateCar\n        capability: deepracer\n        description: Update vehicle name or fleet assignment\n    persona: Event Organizer\n\nrest:\n  port: 8080\n  baseURL: https://deepracer.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: deepracer\n\nmcp:\n  port: 9090\n  tools:\n    - name: evaluate_model_performance\n      description: Review trained reinforcement\
  \ learning models and their performance before submission\n      workflow: Evaluate Model Performance\n    - name: participate_in_leaderboard\n      description: Find active leaderboards, review rankings, and monitor race submission performance\n      workflow: Participate in Leaderboard\n    - name: manage_racing_fleet\n      description: Register, configure, and maintain DeepRacer physical vehicles\n      workflow: Manage Racing Fleet\n    - name: list_models\n      description: List reinforcement learning models for DeepRacer\n      operationId: listModels\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-deepracer/refs/heads/main/capabilities/autonomous-racing-operations.yaml
tags: []
tools: []
---
