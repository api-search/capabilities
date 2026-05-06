---
categories: []
consumed_apis: []
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
- start placement
- get fleet attributes
- request optimal game session placement
- describe scaling policies
- create a new game server build resource
- game session and player session lifecycle
- describe fleet capacity
- get current capacity settings and utilization for a fleet
- create or update a fleet auto-scaling policy
- amazon gamelift
- create build
- describe fleet utilization
- create or update a fleet scaling policy
- describe game sessions
- unified workflow for game infrastructure management
- place game sessions using queue optimization
- fleet auto-scaling policies
- create a fleet alias for traffic routing and fleet transitions
- manage game server fleets
- list builds
- describe fleet
- manages fleet infrastructure, scaling, and deployment pipelines
- get or update a specific fleet
- start game session placement
- list fleets
- game server build and script management
- monitors live game sessions, manages player capacity, and handles incidents
- create game session
- start matchmaking
- get detailed attributes and configuration of a game server fleet
- cloud computing
- manage game sessions
- Game Operations Team
- gaming
- search game sessions
- create a new game server build
- submit a matchmaking request
- describe matchmaking
- cost-optimized spot instance game hosting
- get the status of a matchmaking request
- create player session
- aws
- reserve a player slot in a game session
- list all fleet aliases defined in the region
- DevOps Engineer
- list all fleet aliases
- player matchmaking and flexmatch configuration
- develops and tests multiplayer game server integration with gamelift
- create a new game server fleet
- list all game server fleets
- submit a matchmaking request to find other players and start a game
- start a new game session on a specific fleet
- update fleet capacity
- request optimal placement for a new game session across available fleets
- create alias
- fleet aliases for traffic routing
- fleetiq
- describe fleet events
- list aliases
- manage player slots in game sessions
- list all amazon gamelift game server fleets with their status and configuration
- search for active game sessions with available player slots
- Game Developer
- game server builds
- creating, configuring, and scaling game server fleets
- multiplayer
- game servers
- get active server process, game session, and player statistics for a fleet
- create a new game server fleet with specified configuration
- list all game server builds
- get metadata on specific game sessions
- view logged events for a fleet during a specified time period
- get matchmaking ticket status
- delete a fleet
- list all game server builds uploaded to gamelift
- put scaling policy
- create a fleet alias
- manually adjust fleet capacity settings
- search for active game sessions
- delete fleet
- reserve a player slot in an existing game session
- matchmaking
- create fleet
- start a new game session
- describe fleet attributes
- flexmatch
- player matchmaking operations
- get current auto-scaling policies for a fleet
slug: amazon-gamelift-game-operations
source_filename: amazon-gamelift-game-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon GameLift Game Operations\n  description: Unified workflow capability for game developers and operations teams managing Amazon GameLift resources. Combines\n    fleet management, game session lifecycle, player matchmaking, and scaling operations into a single workflow-oriented interface\n    for multiplayer game infrastructure.\n  tags:\n  - Amazon GameLift\n  - Gaming\n  - Game Servers\n  - Multiplayer\n  - Matchmaking\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-gamelift\n    baseUri: https://gamelift.amazonaws.com\n    description: Amazon GameLift API for game server hosting and management\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_AUTH_HEADER}}'\n   \
  \   placement: header\n    resources:\n    - name: fleets\n      path: /fleets\n      description: Amazon GameLift Fleets operations\n      operations:\n      - name: CreateFleet\n        method: POST\n        description: Amazon GameLift Create Fleet\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateFleetLocations\n        method: POST\n        description: Amazon GameLift Create Fleet Locations\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateLocation\n        method:\
  \ POST\n        description: Amazon GameLift Create Location\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateVpcPeeringAuthorization\n        method: POST\n        description: Amazon GameLift Create Vpc Peering Authorization\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateVpcPeeringConnection\n        method: POST\n        description: Amazon GameLift Create Vpc Peering Connection\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n     \
  \     type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteFleet\n        method: POST\n        description: Amazon GameLift Delete Fleet\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteFleetLocations\n        method: POST\n        description: Amazon GameLift Delete Fleet Locations\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: DeleteLocation\n        method: POST\n        description: Amazon GameLift Delete Location\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteVpcPeeringAuthorization\n        method: POST\n        description: Amazon GameLift Delete Vpc Peering Authorization\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteVpcPeeringConnection\n        method: POST\n        description: Amazon GameLift Delete Vpc Peering Connection\n        inputParameters:\n\
  \        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeEC2InstanceLimits\n        method: POST\n        description: Amazon GameLift Describe E C2 Instance Limits\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetAttributes\n        method: POST\n        description: Amazon GameLift Describe Fleet Attributes\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n\
  \          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetCapacity\n        method: POST\n        description: Amazon GameLift Describe Fleet Capacity\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetEvents\n        method: POST\n        description: Amazon GameLift Describe Fleet Events\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetLocationAttributes\n        method: POST\n        description: Amazon GameLift Describe Fleet Location Attributes\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n        \
  \  required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetLocationCapacity\n        method: POST\n        description: Amazon GameLift Describe Fleet Location Capacity\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetLocationUtilization\n        method: POST\n        description: Amazon GameLift\
  \ Describe Fleet Location Utilization\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetPortSettings\n        method: POST\n        description: Amazon GameLift Describe Fleet Port Settings\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeFleetUtilization\n        method: POST\n        description: Amazon GameLift Describe Fleet Utilization\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n\
  \          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeGameServerInstances\n        method: POST\n        description: Amazon GameLift Describe Game Server Instances\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description:\
  \ X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeInstances\n        method: POST\n        description: Amazon GameLift Describe Instances\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeVpcPeeringAuthorizations\n        method: POST\n        description: Amazon GameLift Describe Vpc Peering Authorizations\n        inputParameters:\n      \
  \  - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeVpcPeeringConnections\n        method: POST\n        description: Amazon GameLift Describe Vpc Peering Connections\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: GetInstanceAccess\n        method: POST\n        description: Amazon GameLift Get Instance Access\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListFleets\n        method: POST\n        description: Amazon GameLift List Fleets\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListLocations\n        method: POST\n        description: Amazon GameLift List Locations\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description:\
  \ Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: StartFleetActions\n        method: POST\n        description: Amazon GameLift Start Fleet Actions\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: StopFleetActions\n        method: POST\n        description: Amazon GameLift Stop Fleet Actions\n        inputParameters:\n        - name: X-Amz-Target\n \
  \         in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: UpdateFleetAttributes\n        method: POST\n        description: Amazon GameLift Update Fleet Attributes\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: UpdateFleetCapacity\n        method: POST\n        description: Amazon GameLift Update Fleet Capacity\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: UpdateFleetPortSettings\n        method: POST\n        description: Amazon GameLift Update Fleet Port Settings\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: game-sessions\n      path: /game-sessions\n      description: Amazon GameLift Game Sessions operations\n      operations:\n      - name: CreateGameSession\n        method: POST\n        description: Amazon GameLift Create Game Session\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: CreateGameSessionQueue\n        method: POST\n        description: Amazon GameLift Create Game Session Queue\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteGameSessionQueue\n        method: POST\n        description: Amazon GameLift Delete Game Session Queue\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeregisterCompute\n        method: POST\n        description: Amazon GameLift Deregister Compute\n        inputParameters:\n        - name:\
  \ X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeCompute\n        method: POST\n        description: Amazon GameLift Describe Compute\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeGameSessionDetails\n        method: POST\n        description: Amazon GameLift Describe Game Session Details\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n     \
  \     type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeGameSessionPlacement\n        method: POST\n        description: Amazon GameLift Describe Game Session Placement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeGameSessionQueues\n        method: POST\n        description: Amazon GameLift Describe Game Session Queues\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n\
  \          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeGameSessions\n        method: POST\n        description: Amazon GameLift Describe Game Sessions\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n \
  \         description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeRuntimeConfiguration\n        method: POST\n        description: Amazon GameLift Describe Runtime Configuration\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: GetComputeAccess\n        method: POST\n        description: Amazon GameLift Get Compute Access\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n     \
  \ - name: GetComputeAuthToken\n        method: POST\n        description: Amazon GameLift Get Compute Auth Token\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: GetGameSessionLogUrl\n        method: POST\n        description: Amazon GameLift Get Game Session Log Url\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListCompute\n        method: POST\n        description: Amazon GameLift List Compute\n        inputParameters:\n        - name: Limit\n          in: query\n          type:\
  \ string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListTagsForResource\n        method: POST\n        description: Amazon GameLift List Tags for Resource\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: RegisterCompute\n        method: POST\n        description: Amazon GameLift Register Compute\n\
  \        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: SearchGameSessions\n        method: POST\n        description: Amazon GameLift Search Game Sessions\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: StartGameSessionPlacement\n\
  \        method: POST\n        description: Amazon GameLift Start Game Session Placement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: StopGameSessionPlacement\n        method: POST\n        description: Amazon GameLift Stop Game Session Placement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: TagResource\n        method: POST\n        description: Amazon GameLift Tag Resource\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n\
  \          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: UntagResource\n        method: POST\n        description: Amazon GameLift Untag Resource\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: UpdateGameSession\n        method: POST\n        description: Amazon GameLift Update Game Session\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: UpdateGameSessionQueue\n        method: POST\n        description: Amazon GameLift Update Game Session Queue\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: UpdateRuntimeConfiguration\n        method: POST\n        description: Amazon GameLift Update Runtime Configuration\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-sessions\n      path: /player-sessions\n      description: Amazon GameLift Player Sessions operations\n      operations:\n      - name: CreatePlayerSession\n\
  \        method: POST\n        description: Amazon GameLift Create Player Session\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreatePlayerSessions\n        method: POST\n        description: Amazon GameLift Create Player Sessions\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribePlayerSessions\n        method: POST\n        description: Amazon GameLift Describe Player Sessions\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n\
  \          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matchmaking\n      path: /matchmaking\n      description: Amazon GameLift Matchmaking operations\n      operations:\n      - name: AcceptMatch\n        method: POST\n        description: Amazon GameLift Accept Match\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \   - name: CreateMatchmakingConfiguration\n        method: POST\n        description: Amazon GameLift Create Matchmaking Configuration\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateMatchmakingRuleSet\n        method: POST\n        description: Amazon GameLift Create Matchmaking Rule Set\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteMatchmakingConfiguration\n        method: POST\n        description: Amazon GameLift Delete Matchmaking Configuration\n        inputParameters:\n\
  \        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteMatchmakingRuleSet\n        method: POST\n        description: Amazon GameLift Delete Matchmaking Rule Set\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeMatchmaking\n        method: POST\n        description: Amazon GameLift Describe Matchmaking\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeMatchmakingConfigurations\n        method: POST\n        description: Amazon GameLift Describe Matchmaking Configurations\n        inputParameters:\n        - name: Limit\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeMatchmakingRuleSets\n        method: POST\n        description: Amazon GameLift Describe Matchmaking Rule Sets\n        inputParameters:\n        - name: Limit\n      \
  \    in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: StartMatchBackfill\n        method: POST\n        description: Amazon GameLift Start Match Backfill\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\n\n# --- truncated at 32 KB (57 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/amazon-gamelift/refs/heads/main/capabilities/amazon-gamelift-game-operations.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-gamelift/refs/heads/main/capabilities/amazon-gamelift-game-operations.yaml
tags:
- Amazon GameLift
- Gaming
- Game Servers
- Multiplayer
- Matchmaking
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
