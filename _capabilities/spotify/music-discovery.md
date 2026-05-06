---
categories: []
consumed_apis: []
description: Workflow capability for Spotify music discovery, playlist building, and personalization. Enables AI assistants and applications to search the catalog, get recommendations, manage playlists, control playback, and access user listening history and preferences. Covers the full music experience lifecycle from discovery through listening.
layout: capability
name: Spotify Music Discovery
operations:
- description: Search for tracks, albums, artists, and playlists
  method: GET
  name: search
  path: /v1/search
- description: Get track details
  method: GET
  name: get-track
  path: /v1/tracks/{id}
- description: Get artist details
  method: GET
  name: get-artist
  path: /v1/artists/{id}
- description: Get album details and tracks
  method: GET
  name: get-album
  path: /v1/albums/{id}
- description: Get track recommendations from seeds
  method: GET
  name: get-recommendations
  path: /v1/recommendations
- description: Get playlist metadata and tracks
  method: GET
  name: get-playlist
  path: /v1/playlists/{playlist_id}
- description: Get tracks in a playlist
  method: GET
  name: get-playlist-items
  path: /v1/playlists/{playlist_id}/items
- description: Add tracks to a playlist
  method: POST
  name: add-to-playlist
  path: /v1/playlists/{playlist_id}/items
- description: Get current user's playlists
  method: GET
  name: get-my-playlists
  path: /v1/me/playlists
- description: Get current playback state
  method: GET
  name: get-playback-state
  path: /v1/player
- description: Start or resume playback
  method: PUT
  name: start-playback
  path: /v1/player/play
- description: Get the playback queue
  method: GET
  name: get-queue
  path: /v1/player/queue
- description: Add a track to the queue
  method: POST
  name: add-to-queue
  path: /v1/player/queue
- description: Get user's top artists or tracks
  method: GET
  name: get-top-items
  path: /v1/me/top/{type}
personas: []
provider_name: Spotify
provider_slug: spotify
search_terms:
- add to queue
- get albums released by an artist, including singles, compilations, and appearances.
- album details
- playlists
- search the spotify music catalog
- get tracks in a playlist
- play music
- user's top artists and tracks
- podcasts
- get the authenticated user's top tracks over short, medium, or long term.
- playback
- audio
- get an artist's profile including genres, popularity, and follower count.
- get the tracks currently in the spotify playback queue.
- get track details
- search
- get track
- get top items
- get top tracks
- search the spotify catalog for tracks, albums, artists, playlists, shows, or episodes. use type='track,album,artist' to search multiple types at once.
- streaming
- get album details and tracks
- personalization
- get artist albums
- get playlist metadata and tracks
- playback queue
- add a track or episode to the spotify playback queue by uri.
- get top artists
- get the current spotify playback state including track, device, position, and shuffle/repeat settings.
- spotify
- get the playback queue
- skip to the next track in the playback queue.
- start or resume spotify playback. can play a specific context (album, playlist, artist) or list of track uris.
- get playback state
- playback state
- get the authenticated user's top artists over short, medium, or long term.
- pause playback
- add to playlist
- add a track to the queue
- track metadata
- search music
- get my playlists
- artist profile
- get playback queue
- get playlist items
- discovery
- playlist details
- start or resume playback
- get playlist details including all tracks, description, and owner.
- get an album's metadata including tracklist, release date, and label.
- get current playback state
- add tracks to playlist
- personalized track recommendations
- get artist
- get detailed metadata for a spotify track including artists, album, duration, and audio features.
- recommendations
- add one or more tracks to a spotify playlist by their uris.
- get user's top artists or tracks
- playlist track management
- get all playlists owned or followed by the authenticated user.
- get the tracks in a playlist with pagination support.
- get track recommendations from seeds
- music
- get recommendations
- get current user's playlists
- get queue
- get playlist
- skip to next
- get playlist tracks
- get artist details
- search for tracks, albums, artists, and playlists
- add tracks to a playlist
- pause spotify playback on the current active device.
- get personalized track recommendations based on seed artists, tracks, and genres. supports audio feature targeting (tempo, energy, danceability).
- current user's playlists
- start playback
- get album
slug: music-discovery
source_filename: music-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spotify Music Discovery\n  description: Workflow capability for Spotify music discovery, playlist building, and personalization. Enables AI assistants\n    and applications to search the catalog, get recommendations, manage playlists, control playback, and access user listening\n    history and preferences. Covers the full music experience lifecycle from discovery through listening.\n  tags:\n  - Spotify\n  - Music\n  - Discovery\n  - Playlists\n  - Recommendations\n  - Playback\n  - Personalization\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPOTIFY_ACCESS_TOKEN: SPOTIFY_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spotify\n    baseUri: https://api.spotify.com/v1\n    description: Spotify Web API for music discovery, library management, and playback control\n    authentication:\n      type: bearer\n      token: '{{SPOTIFY_ACCESS_TOKEN}}'\n    resources:\n    - name:\
  \ search\n      path: /search\n      description: Search Spotify catalog\n      operations:\n      - name: search\n        method: GET\n        description: Search for tracks, albums, artists, playlists, shows, or episodes\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: type\n          in: query\n          type: string\n          required: true\n          description: 'Comma-separated types: track,album,artist,playlist,show,episode'\n        - name: market\n          in: query\n          type: string\n          required: false\n          description: ISO 3166-1 alpha-2 market code\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results per type (1-50)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: track\n      path: /tracks/{id}\n      description: Single track\n      operations:\n      - name: get-track\n        method: GET\n        description: Get a track by Spotify ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Spotify track ID\n        - name: market\n          in: query\n          type: string\n          required: false\n          description: Market for track availability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist\n      path: /artists/{id}\n      description: Single artist\n      operations:\n      - name: get-artist\n        method: GET\n        description: Get an artist by Spotify ID\n        inputParameters:\n        - name: id\n    \
  \      in: path\n          type: string\n          required: true\n          description: Spotify artist ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist-albums\n      path: /artists/{id}/albums\n      description: Artist's albums\n      operations:\n      - name: get-artist-albums\n        method: GET\n        description: Get an artist's albums\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Spotify artist ID\n        - name: include_groups\n          in: query\n          type: string\n          required: false\n          description: 'Comma-separated: album,single,appears_on,compilation'\n        - name: market\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: items\n          type: array\n          value: $.items\n    - name: album\n      path: /albums/{id}\n      description: Single album\n      operations:\n      - name: get-album\n        method: GET\n        description: Get an album by Spotify ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Spotify album ID\n        - name: market\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player\n      path: /me/player\n      description: Playback state and control\n      operations:\n      - name: get-playback-state\n        method: GET\n        description: Get current playback state\n        inputParameters:\n        - name: market\n          in: query\n          type: string\n          required:\
  \ false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: transfer-playback\n        method: PUT\n        description: Transfer playback to a different device\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            device_ids: '{{tools.device_ids}}'\n            play: '{{tools.play}}'\n    - name: player-play\n      path: /me/player/play\n      description: Start or resume playback\n      operations:\n      - name: start-resume-playback\n        method: PUT\n        description: Start or resume playback on the active device\n        inputParameters:\n        - name: device_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n        body:\n          type: json\n          data:\n            context_uri: '{{tools.context_uri}}'\n            uris: '{{tools.uris}}'\n            offset: '{{tools.offset}}'\n    - name: player-pause\n      path: /me/player/pause\n      description: Pause playback\n      operations:\n      - name: pause-playback\n        method: PUT\n        description: Pause playback on the current device\n        inputParameters:\n        - name: device_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-next\n      path: /me/player/next\n      description: Skip to next track\n      operations:\n      - name: skip-to-next\n        method: POST\n        description: Skip to the next track in the queue\n        inputParameters:\n        - name: device_id\n          in: query\n         \
  \ type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-queue\n      path: /me/player/queue\n      description: Playback queue\n      operations:\n      - name: get-queue\n        method: GET\n        description: Get the user's playback queue\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-to-queue\n        method: POST\n        description: Add an item to the playback queue\n        inputParameters:\n        - name: uri\n          in: query\n          type: string\n          required: true\n          description: Spotify URI of item to queue\n        - name: device_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: playlist\n      path: /playlists/{playlist_id}\n      description: Playlist details\n      operations:\n      - name: get-playlist\n        method: GET\n        description: Get a playlist by Spotify ID\n        inputParameters:\n        - name: playlist_id\n          in: path\n          type: string\n          required: true\n          description: Spotify playlist ID\n        - name: market\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlist-items\n      path: /playlists/{playlist_id}/items\n      description: Playlist tracks/items\n      operations:\n      - name: get-playlist-items\n        method: GET\n        description: Get tracks in a playlist\n        inputParameters:\n        - name: playlist_id\n          in: path\n          type: string\n          required:\
  \ true\n        - name: market\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: items\n          type: array\n          value: $.items\n      - name: add-tracks-to-playlist\n        method: POST\n        description: Add tracks to a playlist\n        inputParameters:\n        - name: playlist_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            uris: '{{tools.uris}}'\n            position: '{{tools.position}}'\n    - name: user-playlists\n      path: /me/playlists\n      description: Current\
  \ user's playlists\n      operations:\n      - name: get-my-playlists\n        method: GET\n        description: Get playlists owned or followed by the current user\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: items\n          type: array\n          value: $.items\n    - name: recommendations\n      path: /recommendations\n      description: Track recommendations\n      operations:\n      - name: get-recommendations\n        method: GET\n        description: Get track recommendations based on seeds\n        inputParameters:\n        - name: seed_artists\n          in: query\n          type: string\n          required: false\n          description: Comma-separated artist IDs\n        - name: seed_tracks\n          in: query\n          type: string\n\
  \          required: false\n          description: Comma-separated track IDs\n        - name: seed_genres\n          in: query\n          type: string\n          required: false\n          description: Comma-separated genre names\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: market\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: tracks\n          type: array\n          value: $.tracks\n    - name: user-top\n      path: /me/top/{type}\n      description: User's top artists or tracks\n      operations:\n      - name: get-users-top-items\n        method: GET\n        description: Get the user's top artists or tracks\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: artists or tracks\n        - name: time_range\n          in: query\n  \
  \        type: string\n          required: false\n          description: short_term, medium_term, or long_term\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: items\n          type: array\n          value: $.items\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spotify-discovery-api\n    description: Unified REST API for Spotify music discovery and playback workflows.\n    resources:\n    - path: /v1/search\n      name: catalog-search\n      description: Search the Spotify music catalog\n      operations:\n      - method: GET\n        name: search\n        description: Search for tracks, albums, artists, and playlists\n        call: spotify.search\n        with:\n          q: rest.q\n          type: rest.type\n          limit: rest.limit\n          market: rest.market\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/tracks/{id}\n      name: track\n      description: Track metadata\n      operations:\n      - method: GET\n        name: get-track\n        description: Get track details\n        call: spotify.get-track\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/artists/{id}\n      name: artist\n      description: Artist profile\n      operations:\n      - method: GET\n        name: get-artist\n        description: Get artist details\n        call: spotify.get-artist\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/albums/{id}\n      name: album\n      description: Album details\n      operations:\n      - method: GET\n        name: get-album\n        description: Get album details and tracks\n        call: spotify.get-album\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/recommendations\n      name: recommendations\n      description: Personalized track recommendations\n      operations:\n      - method: GET\n        name: get-recommendations\n        description: Get track recommendations from seeds\n        call: spotify.get-recommendations\n        with:\n          seed_artists: rest.seed_artists\n          seed_tracks: rest.seed_tracks\n          seed_genres: rest.seed_genres\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/playlists/{playlist_id}\n      name: playlist\n      description: Playlist details\n      operations:\n      - method: GET\n        name: get-playlist\n        description: Get playlist metadata and tracks\n        call: spotify.get-playlist\n        with:\n          playlist_id: rest.playlist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/playlists/{playlist_id}/items\n      name: playlist-items\n\
  \      description: Playlist track management\n      operations:\n      - method: GET\n        name: get-playlist-items\n        description: Get tracks in a playlist\n        call: spotify.get-playlist-items\n        with:\n          playlist_id: rest.playlist_id\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-to-playlist\n        description: Add tracks to a playlist\n        call: spotify.add-tracks-to-playlist\n        with:\n          playlist_id: rest.playlist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/me/playlists\n      name: my-playlists\n      description: Current user's playlists\n      operations:\n      - method: GET\n        name: get-my-playlists\n        description: Get current user's playlists\n        call: spotify.get-my-playlists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/player\n\
  \      name: player\n      description: Playback state\n      operations:\n      - method: GET\n        name: get-playback-state\n        description: Get current playback state\n        call: spotify.get-playback-state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/player/play\n      name: player-play\n      description: Start playback\n      operations:\n      - method: PUT\n        name: start-playback\n        description: Start or resume playback\n        call: spotify.start-resume-playback\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/player/queue\n      name: player-queue\n      description: Playback queue\n      operations:\n      - method: GET\n        name: get-queue\n        description: Get the playback queue\n        call: spotify.get-queue\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-to-queue\n        description: Add\
  \ a track to the queue\n        call: spotify.add-to-queue\n        with:\n          uri: rest.uri\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/me/top/{type}\n      name: top-items\n      description: User's top artists and tracks\n      operations:\n      - method: GET\n        name: get-top-items\n        description: Get user's top artists or tracks\n        call: spotify.get-users-top-items\n        with:\n          type: rest.type\n          time_range: rest.time_range\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spotify-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted music discovery, playlist curation, and playback control.\n    tools:\n    - name: search-music\n      description: Search the Spotify catalog for tracks, albums, artists, playlists, shows, or episodes. Use type='track,album,artist'\n        to search multiple types\
  \ at once.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.search\n      with:\n        q: tools.q\n        type: tools.type\n        limit: tools.limit\n        market: tools.market\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track\n      description: Get detailed metadata for a Spotify track including artists, album, duration, and audio features.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-track\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist\n      description: Get an artist's profile including genres, popularity, and follower count.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-artist\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-albums\n      description: Get albums\
  \ released by an artist, including singles, compilations, and appearances.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-artist-albums\n      with:\n        id: tools.id\n        include_groups: tools.include_groups\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-album\n      description: Get an album's metadata including tracklist, release date, and label.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-album\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recommendations\n      description: Get personalized track recommendations based on seed artists, tracks, and genres. Supports audio feature\n        targeting (tempo, energy, danceability).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-recommendations\n      with:\n        seed_artists:\
  \ tools.seed_artists\n        seed_tracks: tools.seed_tracks\n        seed_genres: tools.seed_genres\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-playlist\n      description: Get playlist details including all tracks, description, and owner.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-playlist\n      with:\n        playlist_id: tools.playlist_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-playlist-tracks\n      description: Get the tracks in a playlist with pagination support.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spotify.get-playlist-items\n      with:\n        playlist_id: tools.playlist_id\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-tracks-to-playlist\n      description: Add one or more tracks to a\
  \ Spotify playlist by their URIs.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spotify.add-tracks-to-playlist\n      with:\n        playlist_id: tools.playlist_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-my-playlists\n      description: Get all playlists owned or followed by the authenticated user.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spotify.get-my-playlists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-playback-state\n      description: Get the current Spotify playback state including track, device, position, and shuffle/repeat settings.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spotify.get-playback-state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: play-music\n      description: Start or resume Spotify playback. Can play a specific\
  \ context (album, playlist, artist) or list of track\n        URIs.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spotify.start-resume-playback\n      with:\n        context_uri: tools.context_uri\n        uris: tools.uris\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pause-playback\n      description: Pause Spotify playback on the current active device.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spotify.pause-playback\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: skip-to-next\n      description: Skip to the next track in the playback queue.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spotify.skip-to-next\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-playback-queue\n      description: Get the tracks\
  \ currently in the Spotify playback queue.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spotify.get-queue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-to-queue\n      description: Add a track or episode to the Spotify playback queue by URI.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spotify.add-to-queue\n      with:\n        uri: tools.uri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-artists\n      description: Get the authenticated user's top artists over short, medium, or long term.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spotify.get-users-top-items\n      with:\n        type: artists\n        time_range: tools.time_range\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-tracks\n      description: Get the\
  \ authenticated user's top tracks over short, medium, or long term.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spotify.get-users-top-items\n      with:\n        type: tracks\n        time_range: tools.time_range\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spotify/refs/heads/main/capabilities/music-discovery.yaml
tags:
- Spotify
- Music
- Discovery
- Playlists
- Recommendations
- Playback
- Personalization
tools:
- description: Search the Spotify catalog for tracks, albums, artists, playlists, shows, or episodes. Use type='track,album,artist' to search multiple types at once.
  hints:
    openWorld: true
    readOnly: true
  name: search-music
- description: Get detailed metadata for a Spotify track including artists, album, duration, and audio features.
  hints:
    openWorld: true
    readOnly: true
  name: get-track
- description: Get an artist's profile including genres, popularity, and follower count.
  hints:
    openWorld: true
    readOnly: true
  name: get-artist
- description: Get albums released by an artist, including singles, compilations, and appearances.
  hints:
    openWorld: true
    readOnly: true
  name: get-artist-albums
- description: Get an album's metadata including tracklist, release date, and label.
  hints:
    openWorld: true
    readOnly: true
  name: get-album
- description: Get personalized track recommendations based on seed artists, tracks, and genres. Supports audio feature targeting (tempo, energy, danceability).
  hints:
    openWorld: true
    readOnly: true
  name: get-recommendations
- description: Get playlist details including all tracks, description, and owner.
  hints:
    openWorld: true
    readOnly: true
  name: get-playlist
- description: Get the tracks in a playlist with pagination support.
  hints:
    openWorld: true
    readOnly: true
  name: get-playlist-tracks
- description: Add one or more tracks to a Spotify playlist by their URIs.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-tracks-to-playlist
- description: Get all playlists owned or followed by the authenticated user.
  hints:
    openWorld: false
    readOnly: true
  name: get-my-playlists
- description: Get the current Spotify playback state including track, device, position, and shuffle/repeat settings.
  hints:
    openWorld: false
    readOnly: true
  name: get-playback-state
- description: Start or resume Spotify playback. Can play a specific context (album, playlist, artist) or list of track URIs.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: play-music
- description: Pause Spotify playback on the current active device.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pause-playback
- description: Skip to the next track in the playback queue.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: skip-to-next
- description: Get the tracks currently in the Spotify playback queue.
  hints:
    openWorld: false
    readOnly: true
  name: get-playback-queue
- description: Add a track or episode to the Spotify playback queue by URI.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-to-queue
- description: Get the authenticated user's top artists over short, medium, or long term.
  hints:
    openWorld: false
    readOnly: true
  name: get-top-artists
- description: Get the authenticated user's top tracks over short, medium, or long term.
  hints:
    openWorld: false
    readOnly: true
  name: get-top-tracks
---
