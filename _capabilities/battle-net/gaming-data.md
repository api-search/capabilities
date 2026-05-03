---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Gaming Data
operations: []
personas: []
provider_name: Battle.net
provider_slug: battle-net
search_terms:
- diablo
- oauth token management
- starcraft
- gaming
- players using deck-building tools and card databases
- blizzard
- competitive rankings and season data
- authenticated player-specific data
- games
- developers building companion apps, stat trackers, or tools for blizzard games
- hearthstone
- world of warcraft
- players tracking character progress, gear, and achievements
- static and dynamic game reference data
slug: gaming-data
source_filename: gaming-data.yaml
source_heading: Capability Spec
source_yaml: "capability:\n  name: Battle.net Gaming Data\n  description: >-\n    Battle.net API capabilities for accessing Blizzard Entertainment game data and player\n    profiles across World of Warcraft, Diablo III, Hearthstone, and StarCraft II via\n    OAuth 2.0-secured REST endpoints.\n  categories:\n    - name: World of Warcraft Game Data\n      description: Static and dynamic WoW game data APIs requiring client credentials OAuth.\n      operations:\n        - name: Get Achievement\n          description: Retrieve achievement details by ID.\n        - name: Get Auction House\n          description: Retrieve current auction house listings for a realm.\n        - name: Get Character Classes\n          description: Retrieve list of playable character classes.\n        - name: Get Realm\n          description: Retrieve realm details by slug.\n        - name: Get Item\n          description: Retrieve item details by ID.\n        - name: Get PvP Leaderboard\n          description: Retrieve\
  \ PvP ladder leaderboard for a bracket.\n    - name: World of Warcraft Profile\n      description: Player profile APIs requiring authorization code OAuth with user consent.\n      operations:\n        - name: Get Character Summary\n          description: Retrieve character summary for an authenticated player's character.\n        - name: Get Character Equipment\n          description: Retrieve equipped items for a character.\n        - name: Get Character Achievements\n          description: Retrieve achievement history for a character.\n        - name: Get Mythic Keystone Profile\n          description: Retrieve mythic+ keystone run history for a character.\n    - name: Hearthstone Game Data\n      description: Hearthstone card and deck data APIs.\n      operations:\n        - name: Search Cards\n          description: Search Hearthstone cards with filters for class, set, type, rarity.\n        - name: Get Card\n          description: Retrieve a specific card by ID or slug.\n        -\
  \ name: Get Card Backs\n          description: Retrieve available card back cosmetics.\n        - name: Get Deck\n          description: Retrieve deck information by deck code.\n        - name: Get Metadata\n          description: Retrieve metadata including card sets, classes, types, rarities, keywords.\n    - name: StarCraft II Data\n      description: StarCraft II game data and community profile APIs.\n      operations:\n        - name: Get League Data\n          description: Retrieve league data for a season and game mode.\n        - name: Get Player Profile\n          description: Retrieve StarCraft II player profile data.\n        - name: Get Grandmaster Leaderboard\n          description: Retrieve grandmaster ladder rankings for a region.\n    - name: Diablo III Data\n      description: Diablo III season and era data APIs.\n      operations:\n        - name: Get Season Index\n          description: Retrieve list of available seasons.\n        - name: Get Season Leaderboard\n   \
  \       description: Retrieve leaderboard for a specific season and category.\n        - name: Get Character Profile\n          description: Retrieve Diablo III character profile for a BattleTag.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/battle-net/refs/heads/main/capabilities/gaming-data.yaml
tags: []
tools: []
---
