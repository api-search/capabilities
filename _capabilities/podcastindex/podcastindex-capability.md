---
categories: []
consumed_apis: []
description: 'Download the openapi spec in [json](pi_api.json) or [yaml](pi_api.yaml) format. # Overview The Podcast Index (Podcast Index LLC) is a software developer focused partnership that provides tools and data to anyone who aspires to create new and exciting Podcast experiences without the heavy lifting of indexing, aggregation and data management. # Example Code Users have provided example code for working the API in the following languages: - [AWS Lambda - python](https://github.com/tbowers/python-podcastindex-org-lambda) - [Bash](https://github.com/suorcd/Bash-podcastindex-org-example) - [C#](https'
layout: capability
name: PodcastIndex.org API
operations:
- description: Search
  method: GET
  name: search
  path: /search
- description: Lookup
  method: GET
  name: lookup
  path: /lookup
- description: Search Podcasts
  method: GET
  name: search-byterm
  path: /search/byterm
- description: Search Podcasts by Title
  method: GET
  name: search-bytitle
  path: /search/bytitle
- description: Search Episodes by Person
  method: GET
  name: search-byperson
  path: /search/byperson
- description: Search Music Podcasts
  method: GET
  name: search-music-byterm
  path: /search/music/byterm
- description: By Feed ID
  method: GET
  name: podcasts-byfeedid
  path: /podcasts/byfeedid
- description: By Feed URL
  method: GET
  name: podcasts-byfeedurl
  path: /podcasts/byfeedurl
- description: By iTunes ID
  method: GET
  name: podcasts-byitunesid
  path: /podcasts/byitunesid
- description: By GUID
  method: GET
  name: podcasts-byguid
  path: /podcasts/byguid
- description: By Tag
  method: GET
  name: podcasts-bytag
  path: /podcasts/bytag
- description: By Medium
  method: GET
  name: podcasts-bymedium
  path: /podcasts/bymedium
- description: Trending
  method: GET
  name: podcasts-trending
  path: /podcasts/trending
- description: Dead
  method: GET
  name: podcasts-dead
  path: /podcasts/dead
- description: Batch By Feed GUID
  method: POST
  name: podcasts-batch-byguid
  path: /podcasts/batch/byguid
- description: By Feed ID
  method: GET
  name: episodes-byfeedid
  path: /episodes/byfeedid
- description: By Feed URL
  method: GET
  name: episodes-byfeedurl
  path: /episodes/byfeedurl
- description: By Podcast GUID
  method: GET
  name: episodes-bypodcastguid
  path: /episodes/bypodcastguid
- description: By iTunes ID
  method: GET
  name: episodes-byitunesid
  path: /episodes/byitunesid
- description: By ID
  method: GET
  name: episodes-byid
  path: /episodes/byid
- description: By GUID
  method: GET
  name: episodes-byguid
  path: /episodes/byguid
- description: Live
  method: GET
  name: episodes-live
  path: /episodes/live
- description: Random
  method: GET
  name: episodes-random
  path: /episodes/random
- description: Episodes
  method: GET
  name: recent-episodes
  path: /recent/episodes
- description: Feeds
  method: GET
  name: recent-feeds
  path: /recent/feeds
- description: New Feeds
  method: GET
  name: recent-newfeeds
  path: /recent/newfeeds
- description: New Value Feeds
  method: GET
  name: recent-newvaluefeeds
  path: /recent/newvaluefeeds
- description: Recent Data
  method: GET
  name: recent-data
  path: /recent/data
- description: Soundbites
  method: GET
  name: recent-soundbites
  path: /recent/soundbites
- description: By Feed ID
  method: GET
  name: value-byfeedid
  path: /value/byfeedid
- description: By Feed URL
  method: GET
  name: value-byfeedurl
  path: /value/byfeedurl
- description: By Feed GUID
  method: GET
  name: value-bypodcastguid
  path: /value/bypodcastguid
- description: By Episode GUID
  method: GET
  name: value-byepisodeguid
  path: /value/byepisodeguid
- description: Batch By Episode GUID
  method: POST
  name: value-batch-byepisodeguid
  path: /value/batch/byepisodeguid
- description: Current
  method: GET
  name: stats-current
  path: /stats/current
- description: List
  method: GET
  name: categories-list
  path: /categories/list
- description: Pub Notify
  method: GET
  name: hub-pubnotify
  path: /hub/pubnotify
- description: By Feed URL
  method: GET
  name: add-byfeedurl-get
  path: /add/byfeedurl
- description: By Feed URL
  method: POST
  name: add-byfeedurl-post
  path: /add/byfeedurl
- description: By iTunes ID
  method: GET
  name: add-byitunesid-get
  path: /add/byitunesid
- description: By iTunes ID
  method: POST
  name: add-byitunesid-post
  path: /add/byitunesid
- description: Stats Daily Counts
  method: GET
  name: daily-counts-json
  path: /static/stats/daily_counts.json
- description: Stats Hourly Counts
  method: GET
  name: hourly-counts-json
  path: /static/stats/hourly_counts.json
- description: v4v Sats
  method: GET
  name: chart-data-json
  path: /static/stats/chart-data.json
- description: v4v Music Chart JSON
  method: GET
  name: v4vmusic-json
  path: /static/stats/v4vmusic.json
- description: v4v Music Chart OPML
  method: GET
  name: v4vmusic-opml
  path: /static/stats/v4vmusic.opml
- description: v4v Music Chart RSS
  method: GET
  name: v4vmusic-rss
  path: /static/stats/v4vmusic.rss
- description: Current
  method: GET
  name: current
  path: /static/tracking/current
- description: Feed Value Blocks
  method: GET
  name: feedvalueblocks-json
  path: /static/tracking/feedValueBlocks
- description: Episode Value Blocks
  method: GET
  name: episodevalueblocks-json
  path: /static/tracking/episodeValueBlocks
- description: Dead Feeds
  method: GET
  name: podcastindex-dead-feeds-csv
  path: /static/public/podcastindex_dead_feeds.csv
- description: Feeds Database
  method: GET
  name: podcastindex-feeds-db-tgz
  path: /static/public/podcastindex_feeds.db.tgz
personas: []
provider_name: PodcastIndex
provider_slug: podcastindex
search_terms:
- podcast index
- podcasts batch byguid
- podcasts byfeedid
- lookup
- api
- podcastindex
- episode value blocks
- stats daily counts
- add byitunesid post
- stats hourly counts
- soundbites
- trending
- feed value blocks
- feeds database
- add byfeedurl get
- recent episodes
- batch by episode guid
- episodes live
- recent data
- v4v music chart rss
- search music byterm
- feeds
- value byfeedid
- podcastindex dead feeds csv
- search episodes by person
- podcasts bytag
- episodes byfeedid
- episodes byfeedurl
- podcasts bymedium
- by feed id
- by feed guid
- dead feeds
- hub pubnotify
- podcasts trending
- by itunes id
- v4v music chart json
- v4vmusic opml
- by tag
- batch by feed guid
- new feeds
- categories list
- podcastindex feeds db tgz
- chart data json
- add byitunesid get
- episodes bypodcastguid
- podcasts dead
- v4vmusic json
- recent feeds
- daily counts json
- by feed url
- podcasts byitunesid
- new value feeds
- podcasts byguid
- recent soundbites
- pub notify
- by id
- podcasting
- search music podcasts
- episodes random
- add byfeedurl post
- random
- search podcasts by title
- value bypodcastguid
- by medium
- by episode guid
- episodevalueblocks json
- hourly counts json
- search
- podcasts byfeedurl
- current
- recent newfeeds
- feedvalueblocks json
- search bytitle
- list
- dead
- value batch byepisodeguid
- value byepisodeguid
- value byfeedurl
- episodes byitunesid
- by guid
- search podcasts
- episodes byguid
- live
- v4v music chart opml
- by podcast guid
- discovery
- episodes
- stats current
- v4vmusic rss
- v4v sats
- search byterm
- recent newvaluefeeds
- search byperson
- episodes byid
- open data
slug: podcastindex-capability
source_filename: podcastindex-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PodcastIndex.org API\n  description: 'Download the openapi spec in [json](pi_api.json) or [yaml](pi_api.yaml) format. # Overview The Podcast Index\n    (Podcast Index LLC) is a software developer focused partnership that provides tools and data to anyone who aspires to\n    create new and exciting Podcast experiences without the heavy lifting of indexing, aggregation and data management. #\n    Example Code Users have provided example code for working the API in the following languages: - [AWS Lambda - python](https://github.com/tbowers/python-podcastindex-org-lambda)\n    - [Bash](https://github.com/suorcd/Bash-podcastindex-org-example) - [C#](https'\n  tags:\n  - Podcastindex\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: podcastindex\n    baseUri: https://api.podcastindex.org/api/1.0\n    description: PodcastIndex.org API HTTP API.\n    authentication:\n      type:\
  \ apikey\n      in: header\n      name: User-Agent\n      value: '{{PODCASTINDEX_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      operations:\n      - name: search\n        method: GET\n        description: Search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookup\n      path: /lookup\n      operations:\n      - name: lookup\n        method: GET\n        description: Lookup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-byterm\n      path: /search/byterm\n      operations:\n      - name: search-byterm\n        method: GET\n        description: Search Podcasts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-bytitle\n      path: /search/bytitle\n      operations:\n      - name:\
  \ search-bytitle\n        method: GET\n        description: Search Podcasts by Title\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-byperson\n      path: /search/byperson\n      operations:\n      - name: search-byperson\n        method: GET\n        description: Search Episodes by Person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-music-byterm\n      path: /search/music/byterm\n      operations:\n      - name: search-music-byterm\n        method: GET\n        description: Search Music Podcasts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-byfeedid\n      path: /podcasts/byfeedid\n      operations:\n      - name: podcasts-byfeedid\n        method: GET\n        description: By Feed ID\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-byfeedurl\n      path: /podcasts/byfeedurl\n      operations:\n      - name: podcasts-byfeedurl\n        method: GET\n        description: By Feed URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-byitunesid\n      path: /podcasts/byitunesid\n      operations:\n      - name: podcasts-byitunesid\n        method: GET\n        description: By iTunes ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-byguid\n      path: /podcasts/byguid\n      operations:\n      - name: podcasts-byguid\n        method: GET\n        description: By GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: podcasts-bytag\n      path: /podcasts/bytag\n      operations:\n      - name: podcasts-bytag\n        method: GET\n        description: By Tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-bymedium\n      path: /podcasts/bymedium\n      operations:\n      - name: podcasts-bymedium\n        method: GET\n        description: By Medium\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-trending\n      path: /podcasts/trending\n      operations:\n      - name: podcasts-trending\n        method: GET\n        description: Trending\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-dead\n      path: /podcasts/dead\n      operations:\n      - name: podcasts-dead\n   \
  \     method: GET\n        description: Dead\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcasts-batch-byguid\n      path: /podcasts/batch/byguid\n      operations:\n      - name: podcasts-batch-byguid\n        method: POST\n        description: Batch By Feed GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-byfeedid\n      path: /episodes/byfeedid\n      operations:\n      - name: episodes-byfeedid\n        method: GET\n        description: By Feed ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-byfeedurl\n      path: /episodes/byfeedurl\n      operations:\n      - name: episodes-byfeedurl\n        method: GET\n        description: By Feed URL\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: episodes-bypodcastguid\n      path: /episodes/bypodcastguid\n      operations:\n      - name: episodes-bypodcastguid\n        method: GET\n        description: By Podcast GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-byitunesid\n      path: /episodes/byitunesid\n      operations:\n      - name: episodes-byitunesid\n        method: GET\n        description: By iTunes ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-byid\n      path: /episodes/byid\n      operations:\n      - name: episodes-byid\n        method: GET\n        description: By ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-byguid\n \
  \     path: /episodes/byguid\n      operations:\n      - name: episodes-byguid\n        method: GET\n        description: By GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-live\n      path: /episodes/live\n      operations:\n      - name: episodes-live\n        method: GET\n        description: Live\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: episodes-random\n      path: /episodes/random\n      operations:\n      - name: episodes-random\n        method: GET\n        description: Random\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recent-episodes\n      path: /recent/episodes\n      operations:\n      - name: recent-episodes\n        method: GET\n        description: Episodes\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recent-feeds\n      path: /recent/feeds\n      operations:\n      - name: recent-feeds\n        method: GET\n        description: Feeds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recent-newfeeds\n      path: /recent/newfeeds\n      operations:\n      - name: recent-newfeeds\n        method: GET\n        description: New Feeds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recent-newvaluefeeds\n      path: /recent/newvaluefeeds\n      operations:\n      - name: recent-newvaluefeeds\n        method: GET\n        description: New Value Feeds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recent-data\n\
  \      path: /recent/data\n      operations:\n      - name: recent-data\n        method: GET\n        description: Recent Data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recent-soundbites\n      path: /recent/soundbites\n      operations:\n      - name: recent-soundbites\n        method: GET\n        description: Soundbites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: value-byfeedid\n      path: /value/byfeedid\n      operations:\n      - name: value-byfeedid\n        method: GET\n        description: By Feed ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: value-byfeedurl\n      path: /value/byfeedurl\n      operations:\n      - name: value-byfeedurl\n        method: GET\n        description: By Feed URL\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: value-bypodcastguid\n      path: /value/bypodcastguid\n      operations:\n      - name: value-bypodcastguid\n        method: GET\n        description: By Feed GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: value-byepisodeguid\n      path: /value/byepisodeguid\n      operations:\n      - name: value-byepisodeguid\n        method: GET\n        description: By Episode GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: value-batch-byepisodeguid\n      path: /value/batch/byepisodeguid\n      operations:\n      - name: value-batch-byepisodeguid\n        method: POST\n        description: Batch By Episode GUID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: stats-current\n      path: /stats/current\n      operations:\n      - name: stats-current\n        method: GET\n        description: Current\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-list\n      path: /categories/list\n      operations:\n      - name: categories-list\n        method: GET\n        description: List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hub-pubnotify\n      path: /hub/pubnotify\n      operations:\n      - name: hub-pubnotify\n        method: GET\n        description: Pub Notify\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: add-byfeedurl\n      path: /add/byfeedurl\n      operations:\n      -\
  \ name: add-byfeedurl-get\n        method: GET\n        description: By Feed URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-byfeedurl-post\n        method: POST\n        description: By Feed URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: add-byitunesid\n      path: /add/byitunesid\n      operations:\n      - name: add-byitunesid-get\n        method: GET\n        description: By iTunes ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-byitunesid-post\n        method: POST\n        description: By iTunes ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-stats-daily-counts-json\n      path: /static/stats/daily_counts.json\n\
  \      operations:\n      - name: daily-counts-json\n        method: GET\n        description: Stats Daily Counts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-stats-hourly-counts-json\n      path: /static/stats/hourly_counts.json\n      operations:\n      - name: hourly-counts-json\n        method: GET\n        description: Stats Hourly Counts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-stats-chart-data-json\n      path: /static/stats/chart-data.json\n      operations:\n      - name: chart-data-json\n        method: GET\n        description: v4v Sats\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-stats-v4vmusic-json\n      path: /static/stats/v4vmusic.json\n      operations:\n      - name:\
  \ v4vmusic-json\n        method: GET\n        description: v4v Music Chart JSON\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-stats-v4vmusic-opml\n      path: /static/stats/v4vmusic.opml\n      operations:\n      - name: v4vmusic-opml\n        method: GET\n        description: v4v Music Chart OPML\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-stats-v4vmusic-rss\n      path: /static/stats/v4vmusic.rss\n      operations:\n      - name: v4vmusic-rss\n        method: GET\n        description: v4v Music Chart RSS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-tracking-current\n      path: /static/tracking/current\n      operations:\n      - name: current\n        method: GET\n        description:\
  \ Current\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-tracking-feedvalueblocks\n      path: /static/tracking/feedValueBlocks\n      operations:\n      - name: feedvalueblocks-json\n        method: GET\n        description: Feed Value Blocks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-tracking-episodevalueblocks\n      path: /static/tracking/episodeValueBlocks\n      operations:\n      - name: episodevalueblocks-json\n        method: GET\n        description: Episode Value Blocks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-public-podcastindex-dead-feeds-csv\n      path: /static/public/podcastindex_dead_feeds.csv\n      operations:\n      - name: podcastindex-dead-feeds-csv\n        method:\
  \ GET\n        description: Dead Feeds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: static-public-podcastindex-feeds-db-tgz\n      path: /static/public/podcastindex_feeds.db.tgz\n      operations:\n      - name: podcastindex-feeds-db-tgz\n        method: GET\n        description: Feeds Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: podcastindex-rest\n    description: REST adapter for PodcastIndex.org API.\n    resources:\n    - path: /search\n      name: search\n      operations:\n      - method: GET\n        name: search\n        description: Search\n        call: podcastindex.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lookup\n      name: lookup\n      operations:\n      - method: GET\n       \
  \ name: lookup\n        description: Lookup\n        call: podcastindex.lookup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/byterm\n      name: search-byterm\n      operations:\n      - method: GET\n        name: search-byterm\n        description: Search Podcasts\n        call: podcastindex.search-byterm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/bytitle\n      name: search-bytitle\n      operations:\n      - method: GET\n        name: search-bytitle\n        description: Search Podcasts by Title\n        call: podcastindex.search-bytitle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/byperson\n      name: search-byperson\n      operations:\n      - method: GET\n        name: search-byperson\n        description: Search Episodes by Person\n        call: podcastindex.search-byperson\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /search/music/byterm\n      name: search-music-byterm\n      operations:\n      - method: GET\n        name: search-music-byterm\n        description: Search Music Podcasts\n        call: podcastindex.search-music-byterm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/byfeedid\n      name: podcasts-byfeedid\n      operations:\n      - method: GET\n        name: podcasts-byfeedid\n        description: By Feed ID\n        call: podcastindex.podcasts-byfeedid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/byfeedurl\n      name: podcasts-byfeedurl\n      operations:\n      - method: GET\n        name: podcasts-byfeedurl\n        description: By Feed URL\n        call: podcastindex.podcasts-byfeedurl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/byitunesid\n      name: podcasts-byitunesid\n      operations:\n \
  \     - method: GET\n        name: podcasts-byitunesid\n        description: By iTunes ID\n        call: podcastindex.podcasts-byitunesid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/byguid\n      name: podcasts-byguid\n      operations:\n      - method: GET\n        name: podcasts-byguid\n        description: By GUID\n        call: podcastindex.podcasts-byguid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/bytag\n      name: podcasts-bytag\n      operations:\n      - method: GET\n        name: podcasts-bytag\n        description: By Tag\n        call: podcastindex.podcasts-bytag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/bymedium\n      name: podcasts-bymedium\n      operations:\n      - method: GET\n        name: podcasts-bymedium\n        description: By Medium\n        call: podcastindex.podcasts-bymedium\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /podcasts/trending\n      name: podcasts-trending\n      operations:\n      - method: GET\n        name: podcasts-trending\n        description: Trending\n        call: podcastindex.podcasts-trending\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/dead\n      name: podcasts-dead\n      operations:\n      - method: GET\n        name: podcasts-dead\n        description: Dead\n        call: podcastindex.podcasts-dead\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcasts/batch/byguid\n      name: podcasts-batch-byguid\n      operations:\n      - method: POST\n        name: podcasts-batch-byguid\n        description: Batch By Feed GUID\n        call: podcastindex.podcasts-batch-byguid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/byfeedid\n      name: episodes-byfeedid\n      operations:\n \
  \     - method: GET\n        name: episodes-byfeedid\n        description: By Feed ID\n        call: podcastindex.episodes-byfeedid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/byfeedurl\n      name: episodes-byfeedurl\n      operations:\n      - method: GET\n        name: episodes-byfeedurl\n        description: By Feed URL\n        call: podcastindex.episodes-byfeedurl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/bypodcastguid\n      name: episodes-bypodcastguid\n      operations:\n      - method: GET\n        name: episodes-bypodcastguid\n        description: By Podcast GUID\n        call: podcastindex.episodes-bypodcastguid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/byitunesid\n      name: episodes-byitunesid\n      operations:\n      - method: GET\n        name: episodes-byitunesid\n        description: By iTunes ID\n       \
  \ call: podcastindex.episodes-byitunesid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/byid\n      name: episodes-byid\n      operations:\n      - method: GET\n        name: episodes-byid\n        description: By ID\n        call: podcastindex.episodes-byid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/byguid\n      name: episodes-byguid\n      operations:\n      - method: GET\n        name: episodes-byguid\n        description: By GUID\n        call: podcastindex.episodes-byguid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/live\n      name: episodes-live\n      operations:\n      - method: GET\n        name: episodes-live\n        description: Live\n        call: podcastindex.episodes-live\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /episodes/random\n      name: episodes-random\n      operations:\n\
  \      - method: GET\n        name: episodes-random\n        description: Random\n        call: podcastindex.episodes-random\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recent/episodes\n      name: recent-episodes\n      operations:\n      - method: GET\n        name: recent-episodes\n        description: Episodes\n        call: podcastindex.recent-episodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recent/feeds\n      name: recent-feeds\n      operations:\n      - method: GET\n        name: recent-feeds\n        description: Feeds\n        call: podcastindex.recent-feeds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recent/newfeeds\n      name: recent-newfeeds\n      operations:\n      - method: GET\n        name: recent-newfeeds\n        description: New Feeds\n        call: podcastindex.recent-newfeeds\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /recent/newvaluefeeds\n      name: recent-newvaluefeeds\n      operations:\n      - method: GET\n        name: recent-newvaluefeeds\n        description: New Value Feeds\n        call: podcastindex.recent-newvaluefeeds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recent/data\n      name: recent-data\n      operations:\n      - method: GET\n        name: recent-data\n        description: Recent Data\n        call: podcastindex.recent-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recent/soundbites\n      name: recent-soundbites\n      operations:\n      - method: GET\n        name: recent-soundbites\n        description: Soundbites\n        call: podcastindex.recent-soundbites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /value/byfeedid\n      name: value-byfeedid\n      operations:\n      - method: GET\n        name: value-byfeedid\n\
  \        description: By Feed ID\n        call: podcastindex.value-byfeedid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /value/byfeedurl\n      name: value-byfeedurl\n      operations:\n      - method: GET\n        name: value-byfeedurl\n        description: By Feed URL\n        call: podcastindex.value-byfeedurl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /value/bypodcastguid\n      name: value-bypodcastguid\n      operations:\n      - method: GET\n        name: value-bypodcastguid\n        description: By Feed GUID\n        call: podcastindex.value-bypodcastguid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /value/byepisodeguid\n      name: value-byepisodeguid\n      operations:\n      - method: GET\n        name: value-byepisodeguid\n        description: By Episode GUID\n        call: podcastindex.value-byepisodeguid\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /value/batch/byepisodeguid\n      name: value-batch-byepisodeguid\n      operations:\n      - method: POST\n        name: value-batch-byepisodeguid\n        description: Batch By Episode GUID\n        call: podcastindex.value-batch-byepisodeguid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/current\n      name: stats-current\n      operations:\n      - method: GET\n        name: stats-current\n        description: Current\n        call: podcastindex.stats-current\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/list\n      name: categories-list\n      operations:\n      - method: GET\n        name: categories-list\n        description: List\n        call: podcastindex.categories-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hub/pubnotify\n      name: hub-pubnotify\n      operations:\n      - method:\
  \ GET\n        name: hub-pubnotify\n        description: Pub Notify\n        call: podcastindex.hub-pubnotify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add/byfeedurl\n      name: add-byfeedurl-get\n      operations:\n      - method: GET\n        name: add-byfeedurl-get\n        description: By Feed URL\n        call: podcastindex.add-byfeedurl-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add/byfeedurl\n      name: add-byfeedurl-post\n      operations:\n      - method: POST\n        name: add-byfeedurl-post\n        description: By Feed URL\n        call: podcastindex.add-byfeedurl-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add/byitunesid\n      name: add-byitunesid-get\n      operations:\n      - method: GET\n        name: add-byitunesid-get\n        description: By iTunes ID\n        call: podcastindex.add-byitunesid-get\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /add/byitunesid\n      name: add-byitunesid-post\n      operations:\n      - method: POST\n        name: add-byitunesid-post\n        description: By iTunes ID\n        call: podcastindex.add-byitunesid-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/stats/daily_counts.json\n      name: daily-counts-json\n      operations:\n      - method: GET\n        name: daily-counts-json\n        description: Stats Daily Counts\n        call: podcastindex.daily-counts-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/stats/hourly_counts.json\n      name: hourly-counts-json\n      operations:\n      - method: GET\n        name: hourly-counts-json\n        description: Stats Hourly Counts\n        call: podcastindex.hourly-counts-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/stats/chart-data.json\n\
  \      name: chart-data-json\n      operations:\n      - method: GET\n        name: chart-data-json\n        description: v4v Sats\n        call: podcastindex.chart-data-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/stats/v4vmusic.json\n      name: v4vmusic-json\n      operations:\n      - method: GET\n        name: v4vmusic-json\n        description: v4v Music Chart JSON\n        call: podcastindex.v4vmusic-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/stats/v4vmusic.opml\n      name: v4vmusic-opml\n      operations:\n      - method: GET\n        name: v4vmusic-opml\n        description: v4v Music Chart OPML\n        call: podcastindex.v4vmusic-opml\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/stats/v4vmusic.rss\n      name: v4vmusic-rss\n      operations:\n      - method: GET\n        name: v4vmusic-rss\n        description: v4v\
  \ Music Chart RSS\n        call: podcastindex.v4vmusic-rss\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/tracking/current\n      name: current\n      operations:\n      - method: GET\n        name: current\n        description: Current\n        call: podcastindex.current\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/tracking/feedValueBlocks\n      name: feedvalueblocks-json\n      operations:\n      - method: GET\n        name: feedvalueblocks-json\n        description: Feed Value Blocks\n        call: podcastindex.feedvalueblocks-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/tracking/episodeValueBlocks\n      name: episodevalueblocks-json\n      operations:\n      - method: GET\n        name: episodevalueblocks-json\n        description: Episode Value Blocks\n        call: podcastindex.episodevalueblocks-json\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /static/public/podcastindex_dead_feeds.csv\n      name: podcastindex-dead-feeds-csv\n      operations:\n      - method: GET\n        name: podcastindex-dead-feeds-csv\n        description: Dead Feeds\n        call: podcastindex.podcastindex-dead-feeds-csv\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /static/public/podcastindex_feeds.db.tgz\n      name: podcastindex-feeds-db-tgz\n      operations:\n      - method: GET\n        name: podcastindex-feeds-db-tgz\n        description: Feeds Database\n        call: podcastindex.podcastindex-feeds-db-tgz\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: podcastindex-mcp\n    transport: http\n    description: MCP adapter for PodcastIndex.org API for AI agent use.\n    tools:\n    - name: search\n      description: Search\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: podcastindex.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup\n      description: Lookup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: podcastindex.lookup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-byterm\n      description: Search Podcasts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: podcastindex.search-byterm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-bytitle\n      description: Search Podcasts by Title\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: podcastindex.search-bytitle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-byperson\n      description: Search Episodes by Person\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: podcastindex.search-byperson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-music-byterm\n      description: Search Music Podcasts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: podcastindex.search-music-byterm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: podcasts-byfeedid\n      description: By Feed ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: podcastindex.podcasts-byfeedid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: podcasts-byfeedurl\n      description: By Feed URL\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n  \n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/podcastindex/refs/heads/main/capabilities/podcastindex-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/podcastindex/refs/heads/main/capabilities/podcastindex-capability.yaml
tags:
- Podcastindex
- API
tools:
- description: Search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search
- description: Lookup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lookup
- description: Search Podcasts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-byterm
- description: Search Podcasts by Title
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-bytitle
- description: Search Episodes by Person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-byperson
- description: Search Music Podcasts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-music-byterm
- description: By Feed ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-byfeedid
- description: By Feed URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-byfeedurl
- description: By iTunes ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-byitunesid
- description: By GUID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-byguid
- description: By Tag
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-bytag
- description: By Medium
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-bymedium
- description: Trending
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-trending
- description: Dead
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcasts-dead
- description: Batch By Feed GUID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: podcasts-batch-byguid
- description: By Feed ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-byfeedid
- description: By Feed URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-byfeedurl
- description: By Podcast GUID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-bypodcastguid
- description: By iTunes ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-byitunesid
- description: By ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-byid
- description: By GUID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-byguid
- description: Live
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-live
- description: Random
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodes-random
- description: Episodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: recent-episodes
- description: Feeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: recent-feeds
- description: New Feeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: recent-newfeeds
- description: New Value Feeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: recent-newvaluefeeds
- description: Recent Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: recent-data
- description: Soundbites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: recent-soundbites
- description: By Feed ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: value-byfeedid
- description: By Feed URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: value-byfeedurl
- description: By Feed GUID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: value-bypodcastguid
- description: By Episode GUID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: value-byepisodeguid
- description: Batch By Episode GUID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: value-batch-byepisodeguid
- description: Current
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stats-current
- description: List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: categories-list
- description: Pub Notify
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: hub-pubnotify
- description: By Feed URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: add-byfeedurl-get
- description: By Feed URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-byfeedurl-post
- description: By iTunes ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: add-byitunesid-get
- description: By iTunes ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-byitunesid-post
- description: Stats Daily Counts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: daily-counts-json
- description: Stats Hourly Counts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: hourly-counts-json
- description: v4v Sats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: chart-data-json
- description: v4v Music Chart JSON
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: v4vmusic-json
- description: v4v Music Chart OPML
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: v4vmusic-opml
- description: v4v Music Chart RSS
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: v4vmusic-rss
- description: Current
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: current
- description: Feed Value Blocks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedvalueblocks-json
- description: Episode Value Blocks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: episodevalueblocks-json
- description: Dead Feeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcastindex-dead-feeds-csv
- description: Feeds Database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: podcastindex-feeds-db-tgz
---
