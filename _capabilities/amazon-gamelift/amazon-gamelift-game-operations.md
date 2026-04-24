---
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
- matchmaking
- monitors live game sessions, manages player capacity, and handles incidents
- list all game server builds
- submit a matchmaking request
- get fleet attributes
- start placement
- list fleets
- create player session
- describe fleet capacity
- describe fleet events
- manage game server fleets
- game servers
- game session and player session lifecycle
- delete fleet
- manage game sessions
- request optimal game session placement
- describe matchmaking
- put scaling policy
- flexmatch
- create or update a fleet scaling policy
- get detailed attributes and configuration of a game server fleet
- multiplayer
- create a new game server build
- game server builds
- manually adjust fleet capacity settings
- search game sessions
- manage player slots in game sessions
- get the status of a matchmaking request
- get or update a specific fleet
- reserve a player slot in a game session
- create alias
- describe fleet utilization
- create a new game server fleet with specified configuration
- develops and tests multiplayer game server integration with gamelift
- describe fleet
- view logged events for a fleet during a specified time period
- describe fleet attributes
- search for active game sessions with available player slots
- describe scaling policies
- create fleet
- list all amazon gamelift game server fleets with their status and configuration
- delete a fleet
- create a new game server build resource
- place game sessions using queue optimization
- fleetiq
- fleet auto-scaling policies
- get current auto-scaling policies for a fleet
- create a fleet alias
- player matchmaking and flexmatch configuration
- search for active game sessions
- Game Operations Team
- reserve a player slot in an existing game session
- get current capacity settings and utilization for a fleet
- list all game server fleets
- amazon gamelift
- list all fleet aliases defined in the region
- create build
- create or update a fleet auto-scaling policy
- list all fleet aliases
- submit a matchmaking request to find other players and start a game
- get active server process, game session, and player statistics for a fleet
- list builds
- start a new game session on a specific fleet
- create game session
- fleet aliases for traffic routing
- gaming
- cloud computing
- describe game sessions
- start a new game session
- start matchmaking
- player matchmaking operations
- request optimal placement for a new game session across available fleets
- start game session placement
- list all game server builds uploaded to gamelift
- Game Developer
- get matchmaking ticket status
- unified workflow for game infrastructure management
- get metadata on specific game sessions
- game server build and script management
- create a fleet alias for traffic routing and fleet transitions
- list aliases
- create a new game server fleet
- update fleet capacity
- aws
- cost-optimized spot instance game hosting
- manages fleet infrastructure, scaling, and deployment pipelines
- creating, configuring, and scaling game server fleets
- DevOps Engineer
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
