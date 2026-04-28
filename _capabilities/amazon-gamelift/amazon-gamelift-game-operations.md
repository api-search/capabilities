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
- game server builds
- list all game server builds
- put scaling policy
- submit a matchmaking request to find other players and start a game
- create a new game server build resource
- delete a fleet
- game session and player session lifecycle
- player matchmaking operations
- start matchmaking
- create game session
- search for active game sessions with available player slots
- manage game sessions
- create fleet
- monitors live game sessions, manages player capacity, and handles incidents
- get matchmaking ticket status
- create a new game server fleet with specified configuration
- search game sessions
- create player session
- list all fleet aliases
- manage player slots in game sessions
- delete fleet
- reserve a player slot in a game session
- create alias
- start a new game session
- describe fleet events
- player matchmaking and flexmatch configuration
- Game Developer
- get active server process, game session, and player statistics for a fleet
- manually adjust fleet capacity settings
- request optimal placement for a new game session across available fleets
- unified workflow for game infrastructure management
- aws
- start a new game session on a specific fleet
- create a new game server build
- list fleets
- update fleet capacity
- list all amazon gamelift game server fleets with their status and configuration
- get current auto-scaling policies for a fleet
- describe game sessions
- cloud computing
- manages fleet infrastructure, scaling, and deployment pipelines
- start game session placement
- create a new game server fleet
- get current capacity settings and utilization for a fleet
- get metadata on specific game sessions
- multiplayer
- list all game server fleets
- start placement
- describe matchmaking
- request optimal game session placement
- cost-optimized spot instance game hosting
- view logged events for a fleet during a specified time period
- search for active game sessions
- manage game server fleets
- get or update a specific fleet
- game server build and script management
- Game Operations Team
- create or update a fleet scaling policy
- matchmaking
- game servers
- get detailed attributes and configuration of a game server fleet
- place game sessions using queue optimization
- describe fleet capacity
- fleetiq
- describe fleet attributes
- fleet auto-scaling policies
- create a fleet alias
- create build
- creating, configuring, and scaling game server fleets
- get the status of a matchmaking request
- describe fleet utilization
- list aliases
- describe scaling policies
- fleet aliases for traffic routing
- describe fleet
- flexmatch
- develops and tests multiplayer game server integration with gamelift
- gaming
- list all game server builds uploaded to gamelift
- amazon gamelift
- list all fleet aliases defined in the region
- create a fleet alias for traffic routing and fleet transitions
- create or update a fleet auto-scaling policy
- DevOps Engineer
- submit a matchmaking request
- get fleet attributes
- reserve a player slot in an existing game session
- list builds
slug: amazon-gamelift-game-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon GameLift Game Operations\n  description: >-\n    Unified workflow capability for game developers and operations teams managing\n    Amazon GameLift resources. Combines fleet management, game session lifecycle,\n    player matchmaking, and scaling operations into a single workflow-oriented\n    interface for multiplayer game infrastructure.\n  tags:\n    - Amazon GameLift\n    - Gaming\n    - Game Servers\n    - Multiplayer\n    - Matchmaking\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-gamelift\n      location: ./shared/amazon-gamelift.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gamelift-game-ops-api\n      description: Unified REST API for Amazon GameLift game\
  \ operations management.\n      resources:\n        - path: /v1/fleets\n          name: fleets\n          description: Manage game server fleets\n          operations:\n            - method: GET\n              name: list-fleets\n              description: List all game server fleets\n              call: amazon-gamelift.ListFleets\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-fleet\n              description: Create a new game server fleet\n              call: amazon-gamelift.CreateFleet\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fleets/{fleetId}\n          name: fleet-detail\n          description: Get or update a specific fleet\n          operations:\n            - method: GET\n              name: describe-fleet\n              description: Get fleet attributes\n              call: amazon-gamelift.DescribeFleetAttributes\n\
  \              with:\n                FleetId: \"rest.fleetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-fleet\n              description: Delete a fleet\n              call: amazon-gamelift.DeleteFleet\n              with:\n                FleetId: \"rest.fleetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/game-sessions\n          name: game-sessions\n          description: Manage game sessions\n          operations:\n            - method: POST\n              name: create-game-session\n              description: Start a new game session\n              call: amazon-gamelift.CreateGameSession\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: search-game-sessions\n              description: Search for\
  \ active game sessions\n              call: amazon-gamelift.SearchGameSessions\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/game-sessions/placement\n          name: game-session-placement\n          description: Place game sessions using queue optimization\n          operations:\n            - method: POST\n              name: start-placement\n              description: Request optimal game session placement\n              call: amazon-gamelift.StartGameSessionPlacement\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/player-sessions\n          name: player-sessions\n          description: Manage player slots in game sessions\n          operations:\n            - method: POST\n              name: create-player-session\n              description: Reserve a player slot in a game session\n              call: amazon-gamelift.CreatePlayerSession\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/matchmaking\n          name: matchmaking\n          description: Player matchmaking operations\n          operations:\n            - method: POST\n              name: start-matchmaking\n              description: Submit a matchmaking request\n              call: amazon-gamelift.StartMatchmaking\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: describe-matchmaking\n              description: Get matchmaking ticket status\n              call: amazon-gamelift.DescribeMatchmaking\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scaling-policies\n          name: scaling-policies\n          description: Fleet auto-scaling policies\n          operations:\n            - method: PUT\n              name: put-scaling-policy\n\
  \              description: Create or update a fleet scaling policy\n              call: amazon-gamelift.PutScalingPolicy\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/builds\n          name: builds\n          description: Game server builds\n          operations:\n            - method: GET\n              name: list-builds\n              description: List all game server builds\n              call: amazon-gamelift.ListBuilds\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-build\n              description: Create a new game server build\n              call: amazon-gamelift.CreateBuild\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/aliases\n          name: aliases\n          description: Fleet aliases for traffic routing\n          operations:\n\
  \            - method: GET\n              name: list-aliases\n              description: List all fleet aliases\n              call: amazon-gamelift.ListAliases\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-alias\n              description: Create a fleet alias\n              call: amazon-gamelift.CreateAlias\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: gamelift-game-ops-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon GameLift game infrastructure management.\n      tools:\n        - name: list-fleets\n          description: List all Amazon GameLift game server fleets with their status and configuration\n          hints:\n            readOnly: true\n            openWorld: true\n          call: amazon-gamelift.ListFleets\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-fleet\n          description: Create a new game server fleet with specified configuration\n          hints:\n            readOnly: false\n          call: amazon-gamelift.CreateFleet\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-fleet-attributes\n          description: Get detailed attributes and configuration of a game server fleet\n          hints:\n            readOnly: true\n            idempotent: true\n          call: amazon-gamelift.DescribeFleetAttributes\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-fleet-capacity\n          description: Get current capacity settings and utilization for a fleet\n          hints:\n            readOnly: true\n          call: amazon-gamelift.DescribeFleetCapacity\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: update-fleet-capacity\n          description: Manually adjust fleet capacity settings\n          hints:\n            readOnly: false\n            idempotent: true\n          call: amazon-gamelift.UpdateFleetCapacity\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-game-session\n          description: Start a new game session on a specific fleet\n          hints:\n            readOnly: false\n          call: amazon-gamelift.CreateGameSession\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-game-sessions\n          description: Search for active game sessions with available player slots\n          hints:\n            readOnly: true\n          call: amazon-gamelift.SearchGameSessions\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-game-sessions\n          description:\
  \ Get metadata on specific game sessions\n          hints:\n            readOnly: true\n          call: amazon-gamelift.DescribeGameSessions\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-game-session-placement\n          description: Request optimal placement for a new game session across available fleets\n          hints:\n            readOnly: false\n          call: amazon-gamelift.StartGameSessionPlacement\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-player-session\n          description: Reserve a player slot in an existing game session\n          hints:\n            readOnly: false\n          call: amazon-gamelift.CreatePlayerSession\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-matchmaking\n          description: Submit a matchmaking request to find other players and start a game\n    \
  \      hints:\n            readOnly: false\n          call: amazon-gamelift.StartMatchmaking\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-matchmaking\n          description: Get the status of a matchmaking request\n          hints:\n            readOnly: true\n          call: amazon-gamelift.DescribeMatchmaking\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-scaling-policy\n          description: Create or update a fleet auto-scaling policy\n          hints:\n            readOnly: false\n            idempotent: true\n          call: amazon-gamelift.PutScalingPolicy\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-scaling-policies\n          description: Get current auto-scaling policies for a fleet\n          hints:\n            readOnly: true\n          call: amazon-gamelift.DescribeScalingPolicies\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-builds\n          description: List all game server builds uploaded to GameLift\n          hints:\n            readOnly: true\n          call: amazon-gamelift.ListBuilds\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-build\n          description: Create a new game server build resource\n          hints:\n            readOnly: false\n          call: amazon-gamelift.CreateBuild\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-aliases\n          description: List all fleet aliases defined in the region\n          hints:\n            readOnly: true\n          call: amazon-gamelift.ListAliases\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-alias\n          description: Create a fleet alias for traffic\
  \ routing and fleet transitions\n          hints:\n            readOnly: false\n          call: amazon-gamelift.CreateAlias\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-fleet-utilization\n          description: Get active server process, game session, and player statistics for a fleet\n          hints:\n            readOnly: true\n          call: amazon-gamelift.DescribeFleetUtilization\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-fleet-events\n          description: View logged events for a fleet during a specified time period\n          hints:\n            readOnly: true\n          call: amazon-gamelift.DescribeFleetEvents\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-gamelift/refs/heads/main/capabilities/amazon-gamelift-game-operations.yaml
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
