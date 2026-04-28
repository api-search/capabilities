---
categories: []
consumed_apis:
- amazon-gamelift
description: Unified workflow capability for game developers and operations teams managing Amazon GameLift resources. Combines fleet management, game session lifecycle, player matchmaking, and scaling operations into a single workflow-oriented interface for multiplayer game infrastructure.
layout: capability
name: Amazon GameLift Game Operations
operations:
- description: List all game server fleets
  method: GET
  name: list-fleets
  path: /v1/fleets
- description: Create a new game server fleet
  method: POST
  name: create-fleet
  path: /v1/fleets
- description: Get fleet attributes
  method: GET
  name: describe-fleet
  path: /v1/fleets/{fleetId}
- description: Delete a fleet
  method: DELETE
  name: delete-fleet
  path: /v1/fleets/{fleetId}
- description: Start a new game session
  method: POST
  name: create-game-session
  path: /v1/game-sessions
- description: Search for active game sessions
  method: GET
  name: search-game-sessions
  path: /v1/game-sessions
- description: Request optimal game session placement
  method: POST
  name: start-placement
  path: /v1/game-sessions/placement
- description: Reserve a player slot in a game session
  method: POST
  name: create-player-session
  path: /v1/player-sessions
- description: Submit a matchmaking request
  method: POST
  name: start-matchmaking
  path: /v1/matchmaking
- description: Get matchmaking ticket status
  method: GET
  name: describe-matchmaking
  path: /v1/matchmaking
- description: Create or update a fleet scaling policy
  method: PUT
  name: put-scaling-policy
  path: /v1/scaling-policies
- description: List all game server builds
  method: GET
  name: list-builds
  path: /v1/builds
- description: Create a new game server build
  method: POST
  name: create-build
  path: /v1/builds
- description: List all fleet aliases
  method: GET
  name: list-aliases
  path: /v1/aliases
- description: Create a fleet alias
  method: POST
  name: create-alias
  path: /v1/aliases
personas: []
provider_name: Amazon GameLift
provider_slug: amazon-gamelift
search_terms:
- create a new game server fleet
- list all game server builds uploaded to gamelift
- update fleet capacity
- Game Developer
- start a new game session
- manages fleet infrastructure, scaling, and deployment pipelines
- player matchmaking and flexmatch configuration
- aws
- list all fleet aliases
- create game session
- create a fleet alias
- creating, configuring, and scaling game server fleets
- submit a matchmaking request
- get current auto-scaling policies for a fleet
- flexmatch
- cloud computing
- submit a matchmaking request to find other players and start a game
- list all amazon gamelift game server fleets with their status and configuration
- get detailed attributes and configuration of a game server fleet
- create a fleet alias for traffic routing and fleet transitions
- game session and player session lifecycle
- get matchmaking ticket status
- describe game sessions
- DevOps Engineer
- reserve a player slot in a game session
- get or update a specific fleet
- manually adjust fleet capacity settings
- describe scaling policies
- list all fleet aliases defined in the region
- delete a fleet
- create a new game server build resource
- manage game server fleets
- list aliases
- create fleet
- describe fleet
- create build
- fleet auto-scaling policies
- multiplayer
- fleet aliases for traffic routing
- monitors live game sessions, manages player capacity, and handles incidents
- matchmaking
- start a new game session on a specific fleet
- gaming
- get fleet attributes
- describe fleet capacity
- start game session placement
- delete fleet
- reserve a player slot in an existing game session
- list fleets
- create a new game server build
- create or update a fleet auto-scaling policy
- create a new game server fleet with specified configuration
- fleetiq
- get current capacity settings and utilization for a fleet
- search for active game sessions
- unified workflow for game infrastructure management
- manage game sessions
- create alias
- create player session
- get metadata on specific game sessions
- amazon gamelift
- list builds
- describe fleet attributes
- develops and tests multiplayer game server integration with gamelift
- search for active game sessions with available player slots
- player matchmaking operations
- game server builds
- start placement
- start matchmaking
- manage player slots in game sessions
- get active server process, game session, and player statistics for a fleet
- put scaling policy
- create or update a fleet scaling policy
- list all game server fleets
- place game sessions using queue optimization
- cost-optimized spot instance game hosting
- describe fleet events
- Game Operations Team
- request optimal game session placement
- get the status of a matchmaking request
- describe fleet utilization
- request optimal placement for a new game session across available fleets
- search game sessions
- list all game server builds
- game server build and script management
- view logged events for a fleet during a specified time period
- game servers
- describe matchmaking
slug: amazon-gamelift-game-operations
tags:
- Amazon GameLift
- Gaming
- Game Servers
- Multiplayer
- Matchmaking
- AWS
tools:
- description: List all Amazon GameLift game server fleets with their status and configuration
  hints:
    openWorld: true
    readOnly: true
  name: list-fleets
- description: Create a new game server fleet with specified configuration
  hints:
    readOnly: false
  name: create-fleet
- description: Get detailed attributes and configuration of a game server fleet
  hints:
    idempotent: true
    readOnly: true
  name: describe-fleet-attributes
- description: Get current capacity settings and utilization for a fleet
  hints:
    readOnly: true
  name: describe-fleet-capacity
- description: Manually adjust fleet capacity settings
  hints:
    idempotent: true
    readOnly: false
  name: update-fleet-capacity
- description: Start a new game session on a specific fleet
  hints:
    readOnly: false
  name: create-game-session
- description: Search for active game sessions with available player slots
  hints:
    readOnly: true
  name: search-game-sessions
- description: Get metadata on specific game sessions
  hints:
    readOnly: true
  name: describe-game-sessions
- description: Request optimal placement for a new game session across available fleets
  hints:
    readOnly: false
  name: start-game-session-placement
- description: Reserve a player slot in an existing game session
  hints:
    readOnly: false
  name: create-player-session
- description: Submit a matchmaking request to find other players and start a game
  hints:
    readOnly: false
  name: start-matchmaking
- description: Get the status of a matchmaking request
  hints:
    readOnly: true
  name: describe-matchmaking
- description: Create or update a fleet auto-scaling policy
  hints:
    idempotent: true
    readOnly: false
  name: put-scaling-policy
- description: Get current auto-scaling policies for a fleet
  hints:
    readOnly: true
  name: describe-scaling-policies
- description: List all game server builds uploaded to GameLift
  hints:
    readOnly: true
  name: list-builds
- description: Create a new game server build resource
  hints:
    readOnly: false
  name: create-build
- description: List all fleet aliases defined in the region
  hints:
    readOnly: true
  name: list-aliases
- description: Create a fleet alias for traffic routing and fleet transitions
  hints:
    readOnly: false
  name: create-alias
- description: Get active server process, game session, and player statistics for a fleet
  hints:
    readOnly: true
  name: describe-fleet-utilization
- description: View logged events for a fleet during a specified time period
  hints:
    readOnly: true
  name: describe-fleet-events
---
