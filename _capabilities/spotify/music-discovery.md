---
categories: []
consumed_apis:
- spotify
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
- get playlist
- get artist details
- add one or more tracks to a spotify playlist by their uris.
- user's top artists and tracks
- get track details
- skip to the next track in the playback queue.
- recommendations
- search the spotify catalog for tracks, albums, artists, playlists, shows, or episodes. use type='track,album,artist' to search multiple types at once.
- get current playback state
- get artist
- add tracks to a playlist
- start or resume playback
- get my playlists
- get all playlists owned or followed by the authenticated user.
- get top artists
- search the spotify music catalog
- get track
- get playlist metadata and tracks
- playlist track management
- music
- get top tracks
- get album
- search for tracks, albums, artists, and playlists
- playback queue
- get artist albums
- add a track or episode to the spotify playback queue by uri.
- get the tracks currently in the spotify playback queue.
- pause spotify playback on the current active device.
- current user's playlists
- search
- get detailed metadata for a spotify track including artists, album, duration, and audio features.
- get album details and tracks
- get recommendations
- get queue
- search music
- get playback state
- personalized track recommendations
- skip to next
- get current user's playlists
- track metadata
- get playlist details including all tracks, description, and owner.
- playlist details
- album details
- podcasts
- spotify
- add to queue
- streaming
- artist profile
- get albums released by an artist, including singles, compilations, and appearances.
- audio
- get playlist tracks
- start or resume spotify playback. can play a specific context (album, playlist, artist) or list of track uris.
- get playlist items
- get track recommendations from seeds
- get top items
- get user's top artists or tracks
- playback state
- add to playlist
- pause playback
- get the authenticated user's top tracks over short, medium, or long term.
- get the playback queue
- discovery
- play music
- get playback queue
- get the authenticated user's top artists over short, medium, or long term.
- add a track to the queue
- get the tracks in a playlist with pagination support.
- get an album's metadata including tracklist, release date, and label.
- personalization
- get the current spotify playback state including track, device, position, and shuffle/repeat settings.
- playback
- get personalized track recommendations based on seed artists, tracks, and genres. supports audio feature targeting (tempo, energy, danceability).
- playlists
- start playback
- get an artist's profile including genres, popularity, and follower count.
- get tracks in a playlist
- add tracks to playlist
slug: music-discovery
source_filename: music-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spotify Music Discovery\"\n  description: >-\n    Workflow capability for Spotify music discovery, playlist building, and personalization.\n    Enables AI assistants and applications to search the catalog, get recommendations,\n    manage playlists, control playback, and access user listening history and preferences.\n    Covers the full music experience lifecycle from discovery through listening.\n  tags:\n    - Spotify\n    - Music\n    - Discovery\n    - Playlists\n    - Recommendations\n    - Playback\n    - Personalization\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPOTIFY_ACCESS_TOKEN: SPOTIFY_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: spotify\n      location: ./shared/spotify-web-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spotify-discovery-api\n      description: \"Unified REST API for Spotify music discovery and playback\
  \ workflows.\"\n      resources:\n        - path: /v1/search\n          name: catalog-search\n          description: \"Search the Spotify music catalog\"\n          operations:\n            - method: GET\n              name: search\n              description: \"Search for tracks, albums, artists, and playlists\"\n              call: \"spotify.search\"\n              with:\n                q: \"rest.q\"\n                type: \"rest.type\"\n                limit: \"rest.limit\"\n                market: \"rest.market\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tracks/{id}\n          name: track\n          description: \"Track metadata\"\n          operations:\n            - method: GET\n              name: get-track\n              description: \"Get track details\"\n              call: \"spotify.get-track\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n             \
  \   - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/artists/{id}\n          name: artist\n          description: \"Artist profile\"\n          operations:\n            - method: GET\n              name: get-artist\n              description: \"Get artist details\"\n              call: \"spotify.get-artist\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/albums/{id}\n          name: album\n          description: \"Album details\"\n          operations:\n            - method: GET\n              name: get-album\n              description: \"Get album details and tracks\"\n              call: \"spotify.get-album\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations\n          name: recommendations\n\
  \          description: \"Personalized track recommendations\"\n          operations:\n            - method: GET\n              name: get-recommendations\n              description: \"Get track recommendations from seeds\"\n              call: \"spotify.get-recommendations\"\n              with:\n                seed_artists: \"rest.seed_artists\"\n                seed_tracks: \"rest.seed_tracks\"\n                seed_genres: \"rest.seed_genres\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/playlists/{playlist_id}\n          name: playlist\n          description: \"Playlist details\"\n          operations:\n            - method: GET\n              name: get-playlist\n              description: \"Get playlist metadata and tracks\"\n              call: \"spotify.get-playlist\"\n              with:\n                playlist_id: \"rest.playlist_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/playlists/{playlist_id}/items\n          name: playlist-items\n          description: \"Playlist track management\"\n          operations:\n            - method: GET\n              name: get-playlist-items\n              description: \"Get tracks in a playlist\"\n              call: \"spotify.get-playlist-items\"\n              with:\n                playlist_id: \"rest.playlist_id\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-to-playlist\n              description: \"Add tracks to a playlist\"\n              call: \"spotify.add-tracks-to-playlist\"\n              with:\n                playlist_id: \"rest.playlist_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/me/playlists\n\
  \          name: my-playlists\n          description: \"Current user's playlists\"\n          operations:\n            - method: GET\n              name: get-my-playlists\n              description: \"Get current user's playlists\"\n              call: \"spotify.get-my-playlists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/player\n          name: player\n          description: \"Playback state\"\n          operations:\n            - method: GET\n              name: get-playback-state\n              description: \"Get current playback state\"\n              call: \"spotify.get-playback-state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/player/play\n          name: player-play\n          description: \"Start playback\"\n          operations:\n            - method: PUT\n              name: start-playback\n              description:\
  \ \"Start or resume playback\"\n              call: \"spotify.start-resume-playback\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/player/queue\n          name: player-queue\n          description: \"Playback queue\"\n          operations:\n            - method: GET\n              name: get-queue\n              description: \"Get the playback queue\"\n              call: \"spotify.get-queue\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-to-queue\n              description: \"Add a track to the queue\"\n              call: \"spotify.add-to-queue\"\n              with:\n                uri: \"rest.uri\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/me/top/{type}\n          name: top-items\n          description: \"User's top artists\
  \ and tracks\"\n          operations:\n            - method: GET\n              name: get-top-items\n              description: \"Get user's top artists or tracks\"\n              call: \"spotify.get-users-top-items\"\n              with:\n                type: \"rest.type\"\n                time_range: \"rest.time_range\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spotify-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted music discovery, playlist curation, and playback control.\"\n      tools:\n        - name: search-music\n          description: \"Search the Spotify catalog for tracks, albums, artists, playlists, shows, or episodes. Use type='track,album,artist' to search multiple types at once.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.search\"\n          with:\n            q:\
  \ \"tools.q\"\n            type: \"tools.type\"\n            limit: \"tools.limit\"\n            market: \"tools.market\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-track\n          description: \"Get detailed metadata for a Spotify track including artists, album, duration, and audio features.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-track\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-artist\n          description: \"Get an artist's profile including genres, popularity, and follower count.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-artist\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: get-artist-albums\n          description: \"Get albums released by an artist, including singles, compilations, and appearances.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-artist-albums\"\n          with:\n            id: \"tools.id\"\n            include_groups: \"tools.include_groups\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-album\n          description: \"Get an album's metadata including tracklist, release date, and label.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-album\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-recommendations\n          description: \"Get personalized track recommendations based on seed artists, tracks,\
  \ and genres. Supports audio feature targeting (tempo, energy, danceability).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-recommendations\"\n          with:\n            seed_artists: \"tools.seed_artists\"\n            seed_tracks: \"tools.seed_tracks\"\n            seed_genres: \"tools.seed_genres\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-playlist\n          description: \"Get playlist details including all tracks, description, and owner.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-playlist\"\n          with:\n            playlist_id: \"tools.playlist_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-playlist-tracks\n          description: \"Get the tracks in a playlist with pagination support.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spotify.get-playlist-items\"\n          with:\n            playlist_id: \"tools.playlist_id\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-tracks-to-playlist\n          description: \"Add one or more tracks to a Spotify playlist by their URIs.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"spotify.add-tracks-to-playlist\"\n          with:\n            playlist_id: \"tools.playlist_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-my-playlists\n          description: \"Get all playlists owned or followed by the authenticated user.\"\n          hints:\n            readOnly: true\n            openWorld: false\n\
  \          call: \"spotify.get-my-playlists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-playback-state\n          description: \"Get the current Spotify playback state including track, device, position, and shuffle/repeat settings.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spotify.get-playback-state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: play-music\n          description: \"Start or resume Spotify playback. Can play a specific context (album, playlist, artist) or list of track URIs.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"spotify.start-resume-playback\"\n          with:\n            context_uri: \"tools.context_uri\"\n            uris: \"tools.uris\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: pause-playback\n          description: \"Pause Spotify playback on the current active device.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"spotify.pause-playback\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: skip-to-next\n          description: \"Skip to the next track in the playback queue.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"spotify.skip-to-next\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-playback-queue\n          description: \"Get the tracks currently in the Spotify playback queue.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spotify.get-queue\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: add-to-queue\n          description: \"Add a track or episode to the Spotify playback queue by URI.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"spotify.add-to-queue\"\n          with:\n            uri: \"tools.uri\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-top-artists\n          description: \"Get the authenticated user's top artists over short, medium, or long term.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spotify.get-users-top-items\"\n          with:\n            type: \"artists\"\n            time_range: \"tools.time_range\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-top-tracks\n          description:\
  \ \"Get the authenticated user's top tracks over short, medium, or long term.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spotify.get-users-top-items\"\n          with:\n            type: \"tracks\"\n            time_range: \"tools.time_range\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
