---
categories: []
consumed_apis: []
description: Unified game data workflow for accessing World of Warcraft characters, realms, guilds, items, Hearthstone cards, Diablo III profiles, and StarCraft II ladder data. Used by game developers, community app builders, and gaming analytics teams.
layout: capability
name: Activision Blizzard Game Data
operations:
- description: Get a WoW character profile
  method: GET
  name: get-wow-character
  path: /v1/wow/characters/{realmSlug}/{characterName}
- description: Get WoW realm list
  method: GET
  name: get-wow-realms
  path: /v1/wow/realms
- description: Search Hearthstone cards
  method: GET
  name: search-hearthstone-cards
  path: /v1/hearthstone/cards
- description: Get Diablo III career profile
  method: GET
  name: get-diablo-profile
  path: /v1/diablo/profiles/{battletag}
personas: []
provider_name: activision-blizzard
provider_slug: activision-blizzard
search_terms:
- get the achievements completed by a world of warcraft character
- get the list of world of warcraft realms
- get wow character achievements
- get a world of warcraft character profile including level, class, race, guild, and achievement points
- builds community tools, addons, and apps using battle.net game data
- get diablo iii career profile
- creates fan websites, discord bots, and companion apps using game data
- world of warcraft
- world of warcraft realms
- analyzes game statistics, leaderboards, and player performance data
- starcraft
- get wow realm list
- gaming
- search hearthstone cards
- activision blizzard
- access wow characters/realms, hearthstone cards, diablo iii profiles, and starcraft ii ladder data
- static and dynamic game data apis for community development
- diablo iii profiles
- battle.net
- hearthstone
- get diablo profile
- get a specific hearthstone card by id or slug
- get wow character
- get a wow character profile
- hearthstone card data
- Fan App Builder
- world of warcraft character data
- video game data and player profiles across blizzard franchises
- Community Developer
- Game Analyst
- get wow realms
- get diablo career profile
- get a diablo iii career profile for a battletag account
- diablo
- search hearthstone cards by class, set, mana cost, or other criteria
- get hearthstone card
slug: game-data
source_filename: game-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Activision Blizzard Game Data\n  description: Unified game data workflow for accessing World of Warcraft characters, realms, guilds, items, Hearthstone cards,\n    Diablo III profiles, and StarCraft II ladder data. Used by game developers, community app builders, and gaming analytics\n    teams.\n  tags:\n  - Activision Blizzard\n  - Battle.net\n  - Gaming\n  - World of Warcraft\n  - Hearthstone\n  - Diablo\n  - StarCraft\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BATTLENET_CLIENT_ID: BATTLENET_CLIENT_ID\n    BATTLENET_CLIENT_SECRET: BATTLENET_CLIENT_SECRET\n    BATTLENET_ACCESS_TOKEN: BATTLENET_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: battle-net\n    baseUri: https://us.api.blizzard.com\n    description: Battle.net US region API\n    authentication:\n      type: bearer\n      token: '{{BATTLENET_ACCESS_TOKEN}}'\n    resources:\n    - name: wow-character\n  \
  \    path: /profile/wow/character\n      description: World of Warcraft character data\n      operations:\n      - name: get-character\n        method: GET\n        description: Get a WoW character profile\n        inputParameters:\n        - name: realmSlug\n          in: path\n          type: string\n          required: true\n          description: Realm slug\n        - name: characterName\n          in: path\n          type: string\n          required: true\n          description: Character name\n        - name: namespace\n          in: query\n          type: string\n          required: true\n          description: Namespace (e.g. profile-us)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-character-achievements\n        method: GET\n        description: Get character achievements\n        inputParameters:\n        - name: realmSlug\n          in: path\n          type: string\n        \
  \  required: true\n          description: Realm slug\n        - name: characterName\n          in: path\n          type: string\n          required: true\n          description: Character name\n        - name: namespace\n          in: query\n          type: string\n          required: true\n          description: Namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wow-realm\n      path: /data/wow/realm\n      description: World of Warcraft realm data\n      operations:\n      - name: get-realms-index\n        method: GET\n        description: Get index of all WoW realms\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: true\n          description: Namespace (e.g. dynamic-us)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hearthstone-cards\n\
  \      path: /hearthstone/cards\n      description: Hearthstone card data\n      operations:\n      - name: search-cards\n        method: GET\n        description: Search Hearthstone cards\n        inputParameters:\n        - name: set\n          in: query\n          type: string\n          required: false\n          description: Card set filter\n        - name: class\n          in: query\n          type: string\n          required: false\n          description: Class filter\n        - name: manaCost\n          in: query\n          type: integer\n          required: false\n          description: Mana cost filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-card\n        method: GET\n        description: Get a specific Hearthstone card\n        inputParameters:\n\
  \        - name: idOrSlug\n          in: path\n          type: string\n          required: true\n          description: Card ID or slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diablo-profile\n      path: /d3/profile\n      description: Diablo III profile data\n      operations:\n      - name: get-career-profile\n        method: GET\n        description: Get a Diablo III career profile\n        inputParameters:\n        - name: battletag\n          in: path\n          type: string\n          required: true\n          description: Player BattleTag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: game-data-api\n    description: Unified REST API for Activision Blizzard game data.\n    resources:\n    - path: /v1/wow/characters/{realmSlug}/{characterName}\n\
  \      name: wow-characters\n      description: World of Warcraft character data\n      operations:\n      - method: GET\n        name: get-wow-character\n        description: Get a WoW character profile\n        call: battle-net.get-character\n        with:\n          realmSlug: rest.realmSlug\n          characterName: rest.characterName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/wow/realms\n      name: wow-realms\n      description: World of Warcraft realms\n      operations:\n      - method: GET\n        name: get-wow-realms\n        description: Get WoW realm list\n        call: battle-net.get-realms-index\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hearthstone/cards\n      name: hearthstone-cards\n      description: Hearthstone card data\n      operations:\n      - method: GET\n        name: search-hearthstone-cards\n        description: Search Hearthstone cards\n        call: battle-net.search-cards\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/diablo/profiles/{battletag}\n      name: diablo-profiles\n      description: Diablo III profiles\n      operations:\n      - method: GET\n        name: get-diablo-profile\n        description: Get Diablo III career profile\n        call: battle-net.get-career-profile\n        with:\n          battletag: rest.battletag\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: game-data-mcp\n    transport: http\n    description: MCP server for AI-assisted access to Activision Blizzard game data.\n    tools:\n    - name: get-wow-character\n      description: Get a World of Warcraft character profile including level, class, race, guild, and achievement points\n      hints:\n        readOnly: true\n        openWorld: true\n      call: battle-net.get-character\n      with:\n        realmSlug: tools.realmSlug\n        characterName: tools.characterName\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-wow-character-achievements\n      description: Get the achievements completed by a World of Warcraft character\n      hints:\n        readOnly: true\n        openWorld: true\n      call: battle-net.get-character-achievements\n      with:\n        realmSlug: tools.realmSlug\n        characterName: tools.characterName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-wow-realms\n      description: Get the list of World of Warcraft realms\n      hints:\n        readOnly: true\n        openWorld: true\n      call: battle-net.get-realms-index\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-hearthstone-cards\n      description: Search Hearthstone cards by class, set, mana cost, or other criteria\n      hints:\n        readOnly: true\n        openWorld: true\n      call: battle-net.search-cards\n      with:\n        class: tools.class\n\
  \        set: tools.set\n        manaCost: tools.manaCost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hearthstone-card\n      description: Get a specific Hearthstone card by ID or slug\n      hints:\n        readOnly: true\n        openWorld: false\n      call: battle-net.get-card\n      with:\n        idOrSlug: tools.idOrSlug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-diablo-career-profile\n      description: Get a Diablo III career profile for a BattleTag account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: battle-net.get-career-profile\n      with:\n        battletag: tools.battletag\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/activision-blizzard/refs/heads/main/capabilities/game-data.yaml
tags:
- Activision Blizzard
- Battle.net
- Gaming
- World of Warcraft
- Hearthstone
- Diablo
- StarCraft
tools:
- description: Get a World of Warcraft character profile including level, class, race, guild, and achievement points
  hints:
    openWorld: true
    readOnly: true
  name: get-wow-character
- description: Get the achievements completed by a World of Warcraft character
  hints:
    openWorld: true
    readOnly: true
  name: get-wow-character-achievements
- description: Get the list of World of Warcraft realms
  hints:
    openWorld: true
    readOnly: true
  name: get-wow-realms
- description: Search Hearthstone cards by class, set, mana cost, or other criteria
  hints:
    openWorld: true
    readOnly: true
  name: search-hearthstone-cards
- description: Get a specific Hearthstone card by ID or slug
  hints:
    openWorld: false
    readOnly: true
  name: get-hearthstone-card
- description: Get a Diablo III career profile for a BattleTag account
  hints:
    openWorld: true
    readOnly: true
  name: get-diablo-career-profile
---
