---
categories: []
consumed_apis:
- battle-net
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
- world of warcraft realms
- get diablo profile
- get a world of warcraft character profile including level, class, race, guild, and achievement points
- get the achievements completed by a world of warcraft character
- get a specific hearthstone card by id or slug
- hearthstone card data
- get the list of world of warcraft realms
- gaming
- get diablo iii career profile
- static and dynamic game data apis for community development
- world of warcraft character data
- Game Analyst
- world of warcraft
- battle.net
- get hearthstone card
- builds community tools, addons, and apps using battle.net game data
- diablo
- hearthstone
- search hearthstone cards by class, set, mana cost, or other criteria
- get a diablo iii career profile for a battletag account
- analyzes game statistics, leaderboards, and player performance data
- access wow characters/realms, hearthstone cards, diablo iii profiles, and starcraft ii ladder data
- search hearthstone cards
- get diablo career profile
- Community Developer
- Fan App Builder
- activision blizzard
- creates fan websites, discord bots, and companion apps using game data
- diablo iii profiles
- get wow realms
- get a wow character profile
- get wow character achievements
- get wow character
- video game data and player profiles across blizzard franchises
- get wow realm list
- starcraft
slug: game-data
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Activision Blizzard Game Data\"\n  description: \"Unified game data workflow for accessing World of Warcraft characters, realms, guilds, items, Hearthstone cards, Diablo III profiles, and StarCraft II ladder data. Used by game developers, community app builders, and gaming analytics teams.\"\n  tags:\n    - Activision Blizzard\n    - Battle.net\n    - Gaming\n    - World of Warcraft\n    - Hearthstone\n    - Diablo\n    - StarCraft\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BATTLENET_CLIENT_ID: BATTLENET_CLIENT_ID\n      BATTLENET_CLIENT_SECRET: BATTLENET_CLIENT_SECRET\n      BATTLENET_ACCESS_TOKEN: BATTLENET_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: battle-net\n      location: ./shared/battle-net.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: game-data-api\n      description: \"Unified REST API for Activision Blizzard game data.\"\
  \n      resources:\n        - path: /v1/wow/characters/{realmSlug}/{characterName}\n          name: wow-characters\n          description: \"World of Warcraft character data\"\n          operations:\n            - method: GET\n              name: get-wow-character\n              description: \"Get a WoW character profile\"\n              call: \"battle-net.get-character\"\n              with:\n                realmSlug: \"rest.realmSlug\"\n                characterName: \"rest.characterName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/wow/realms\n          name: wow-realms\n          description: \"World of Warcraft realms\"\n          operations:\n            - method: GET\n              name: get-wow-realms\n              description: \"Get WoW realm list\"\n              call: \"battle-net.get-realms-index\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/hearthstone/cards\n          name: hearthstone-cards\n          description: \"Hearthstone card data\"\n          operations:\n            - method: GET\n              name: search-hearthstone-cards\n              description: \"Search Hearthstone cards\"\n              call: \"battle-net.search-cards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/diablo/profiles/{battletag}\n          name: diablo-profiles\n          description: \"Diablo III profiles\"\n          operations:\n            - method: GET\n              name: get-diablo-profile\n              description: \"Get Diablo III career profile\"\n              call: \"battle-net.get-career-profile\"\n              with:\n                battletag: \"rest.battletag\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: game-data-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted access to Activision Blizzard game data.\"\n      tools:\n        - name: get-wow-character\n          description: \"Get a World of Warcraft character profile including level, class, race, guild, and achievement points\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"battle-net.get-character\"\n          with:\n            realmSlug: \"tools.realmSlug\"\n            characterName: \"tools.characterName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-wow-character-achievements\n          description: \"Get the achievements completed by a World of Warcraft character\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"battle-net.get-character-achievements\"\n          with:\n            realmSlug: \"tools.realmSlug\"\n            characterName: \"tools.characterName\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-wow-realms\n          description: \"Get the list of World of Warcraft realms\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"battle-net.get-realms-index\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-hearthstone-cards\n          description: \"Search Hearthstone cards by class, set, mana cost, or other criteria\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"battle-net.search-cards\"\n          with:\n            class: \"tools.class\"\n            set: \"tools.set\"\n            manaCost: \"tools.manaCost\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hearthstone-card\n          description: \"Get a specific Hearthstone card by ID or slug\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"battle-net.get-card\"\n          with:\n            idOrSlug: \"tools.idOrSlug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-diablo-career-profile\n          description: \"Get a Diablo III career profile for a BattleTag account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"battle-net.get-career-profile\"\n          with:\n            battletag: \"tools.battletag\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
