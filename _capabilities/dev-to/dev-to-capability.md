---
categories: []
consumed_apis: []
description: The Dev.to Forem API (v1) is a RESTful API that provides programmatic access to the Dev.to developer community platform, which is built on the open-source Forem framework. The API enables developers to create, read, update, and manage articles, comments, users, organizations, tags, followers, listings, podcast episodes, pages, display ads, reactions, reading lists, and webhooks. It uses API key authentication, requires an accept header of application/vnd.forem.api-v1+json, and returns JSON responses. Unauthenticated endpoints are CORS-enabled, making it possible to fetch public content directl
layout: capability
name: Dev.to Forem API
operations:
- description: Publish article
  method: POST
  name: createarticle
  path: /articles
- description: Published articles
  method: GET
  name: getarticles
  path: /articles
- description: Published articles sorted by published date
  method: GET
  name: getlatestarticles
  path: /articles/latest
- description: Published article by id
  method: GET
  name: getarticlebyid
  path: /articles/{id}
- description: Update an article by id
  method: PUT
  name: updatearticle
  path: /articles/{id}
- description: Published article by path
  method: GET
  name: getarticlebypath
  path: /articles/{username}/{slug}
- description: User's articles
  method: GET
  name: getuserarticles
  path: /articles/me
- description: User's published articles
  method: GET
  name: getuserpublishedarticles
  path: /articles/me/published
- description: User's unpublished articles
  method: GET
  name: getuserunpublishedarticles
  path: /articles/me/unpublished
- description: User's all articles
  method: GET
  name: getuserallarticles
  path: /articles/me/all
- description: Unpublish an article
  method: PUT
  name: unpublisharticle
  path: /articles/{id}/unpublish
- description: Comments
  method: GET
  name: getcommentsbyarticleid
  path: /comments
- description: Comment by id
  method: GET
  name: getcommentbyid
  path: /comments/{id}
- description: Display ads
  method: GET
  name: getdisplayads
  path: /display_ads
- description: Create display ad
  method: POST
  name: createdisplayad
  path: /display_ads
- description: Display ad
  method: GET
  name: getdisplayadbyid
  path: /display_ads/{id}
- description: Update display ad
  method: PUT
  name: updatedisplayad
  path: /display_ads/{id}
- description: Unpublish display ad
  method: PUT
  name: unpublishdisplayad
  path: /display_ads/{id}/unpublish
- description: Followed Tags
  method: GET
  name: getfollowedtags
  path: /follows/tags
- description: Followers
  method: GET
  name: getfollowers
  path: /followers/users
- description: An organization
  method: GET
  name: getorganization
  path: /organizations/{username}
- description: Organization's users
  method: GET
  name: getorgusers
  path: /organizations/{username}/users
- description: Organization's Articles
  method: GET
  name: getorgarticles
  path: /organizations/{username}/articles
- description: Show details for all pages
  method: GET
  name: getpages
  path: /pages
- description: Create a new page
  method: POST
  name: createpage
  path: /pages
- description: Show details for a page
  method: GET
  name: getpagebyid
  path: /pages/{id}
- description: Update details for a page
  method: PUT
  name: updatepage
  path: /pages/{id}
- description: Remove a page
  method: DELETE
  name: deletepage
  path: /pages/{id}
- description: Podcast Episodes
  method: GET
  name: getpodcastepisodes
  path: /podcast_episodes
- description: A Users or organizations profile image
  method: GET
  name: getprofileimage
  path: /profile_images/{username}
- description: Toggle reaction
  method: POST
  name: togglereaction
  path: /reactions/toggle
- description: Create reaction
  method: POST
  name: createreaction
  path: /reactions
- description: Readinglist
  method: GET
  name: getreadinglist
  path: /readinglist
- description: Tags
  method: GET
  name: gettags
  path: /tags
- description: The authenticated user
  method: GET
  name: getuserme
  path: /users/me
- description: A User
  method: GET
  name: getuser
  path: /users/{id}
- description: Unpublish a User's Articles and Comments
  method: PUT
  name: unpublishuser
  path: /users/{id}/unpublish
- description: Suspend a User
  method: PUT
  name: suspenduser
  path: /users/{id}/suspend
- description: Webhooks
  method: GET
  name: getwebhooks
  path: /webhooks
- description: Create a webhook
  method: POST
  name: createwebhook
  path: /webhooks
- description: A webhook endpoint
  method: GET
  name: getwebhookbyid
  path: /webhooks/{id}
- description: Delete a webhook endpoint
  method: DELETE
  name: deletewebhook
  path: /webhooks/{id}
personas: []
provider_name: dev-to
provider_slug: dev-to
search_terms:
- createdisplayad
- getuserpublishedarticles
- create display ad
- unpublish display ad
- user's unpublished articles
- unpublishdisplayad
- display ad
- readinglist
- getcommentsbyarticleid
- getfollowers
- getprofileimage
- create a new page
- show details for all pages
- api
- a users or organizations profile image
- createwebhook
- display ads
- getreadinglist
- update display ad
- getuser
- updatearticle
- getdisplayadbyid
- unpublishuser
- published article by id
- published articles
- update details for a page
- organization's articles
- updatepage
- show details for a page
- getuserarticles
- delete a webhook endpoint
- update an article by id
- deletepage
- updatedisplayad
- unpublisharticle
- getorganization
- getarticlebypath
- create a webhook
- followers
- createarticle
- togglereaction
- createreaction
- suspend a user
- getdisplayads
- published article by path
- webhooks
- followed tags
- getorgarticles
- getcommentbyid
- a user
- an organization
- getpagebyid
- toggle reaction
- getuserme
- getfollowedtags
- comment by id
- comments
- getuserallarticles
- the authenticated user
- getarticles
- getpodcastepisodes
- user's published articles
- getarticlebyid
- unpublish a user's articles and comments
- getlatestarticles
- user's articles
- publish article
- tags
- getpages
- createpage
- getuserunpublishedarticles
- getwebhooks
- published articles sorted by published date
- unpublish an article
- getwebhookbyid
- organization's users
- getorgusers
- create reaction
- gettags
- dev
- deletewebhook
- user's all articles
- podcast episodes
- to
- remove a page
- suspenduser
- a webhook endpoint
slug: dev-to-capability
source_filename: dev-to-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dev.to Forem API\n  description: The Dev.to Forem API (v1) is a RESTful API that provides programmatic access to the Dev.to developer community\n    platform, which is built on the open-source Forem framework. The API enables developers to create, read, update, and manage\n    articles, comments, users, organizations, tags, followers, listings, podcast episodes, pages, display ads, reactions,\n    reading lists, and webhooks. It uses API key authentication, requires an accept header of application/vnd.forem.api-v1+json,\n    and returns JSON responses. Unauthenticated endpoints are CORS-enabled, making it possible to fetch public content directl\n  tags:\n  - Dev\n  - To\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: dev-to\n    baseUri: https://dev.to/api\n    description: Dev.to Forem API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n     \
  \ name: api-key\n      value: '{{DEV_TO_TOKEN}}'\n    resources:\n    - name: articles\n      path: /articles\n      operations:\n      - name: createarticle\n        method: POST\n        description: Publish article\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getarticles\n        method: GET\n        description: Published articles\n        inputParameters:\n        - name: tag\n          in: query\n          type: string\n          description: Filter articles by a single tag name.\n        - name: tags\n          in: query\n          type: string\n          description: Filter articles by a comma-separated list of tag names (articles must have all specified tags).\n        - name: tags_exclude\n          in: query\n          type: string\n          description: Exclude articles with these comma-separated tag names.\n        - name: username\n          in: query\n          type: string\n\
  \          description: Filter articles by the author's username.\n        - name: state\n          in: query\n          type: string\n          description: Filter articles by state. Defaults to the most popular articles.\n        - name: top\n          in: query\n          type: integer\n          description: Return the most popular articles published in the last N days.\n        - name: collection_id\n          in: query\n          type: integer\n          description: Return articles belonging to the specified collection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-latest\n      path: /articles/latest\n      operations:\n      - name: getlatestarticles\n        method: GET\n        description: Published articles sorted by published date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-id\n\
  \      path: /articles/{id}\n      operations:\n      - name: getarticlebyid\n        method: GET\n        description: Published article by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatearticle\n        method: PUT\n        description: Update an article by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-username-slug\n      path: /articles/{username}/{slug}\n      operations:\n      - name: getarticlebypath\n        method: GET\n        description: Published article by path\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username of the article's author.\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The slug\
  \ of the article.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-me\n      path: /articles/me\n      operations:\n      - name: getuserarticles\n        method: GET\n        description: User's articles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-me-published\n      path: /articles/me/published\n      operations:\n      - name: getuserpublishedarticles\n        method: GET\n        description: User's published articles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-me-unpublished\n      path: /articles/me/unpublished\n      operations:\n      - name: getuserunpublishedarticles\n        method: GET\n        description: User's unpublished articles\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-me-all\n      path: /articles/me/all\n      operations:\n      - name: getuserallarticles\n        method: GET\n        description: User's all articles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-id-unpublish\n      path: /articles/{id}/unpublish\n      operations:\n      - name: unpublisharticle\n        method: PUT\n        description: Unpublish an article\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /comments\n      operations:\n      - name: getcommentsbyarticleid\n        method: GET\n        description: Comments\n        inputParameters:\n        - name: a_id\n          in: query\n          type: integer\n          description: The article ID to\
  \ retrieve comments for.\n        - name: p_id\n          in: query\n          type: integer\n          description: The podcast episode ID to retrieve comments for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments-id\n      path: /comments/{id}\n      operations:\n      - name: getcommentbyid\n        method: GET\n        description: Comment by id\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: display-ads\n      path: /display_ads\n      operations:\n      - name: getdisplayads\n        method: GET\n        description: Display ads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createdisplayad\n        method: POST\n        description: Create display ad\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: display-ads-id\n      path: /display_ads/{id}\n      operations:\n      - name: getdisplayadbyid\n        method: GET\n        description: Display ad\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the display ad.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedisplayad\n        method: PUT\n        description: Update display ad\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the display ad.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: display-ads-id-unpublish\n      path: /display_ads/{id}/unpublish\n      operations:\n      - name: unpublishdisplayad\n        method: PUT\n        description: Unpublish display ad\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the display ad.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: follows-tags\n      path: /follows/tags\n      operations:\n      - name: getfollowedtags\n        method: GET\n        description: Followed Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: followers-users\n      path: /followers/users\n      operations:\n      - name: getfollowers\n        method: GET\n        description: Followers\n\
  \        inputParameters:\n        - name: sort\n          in: query\n          type: string\n          description: Sort order for followers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-username\n      path: /organizations/{username}\n      operations:\n      - name: getorganization\n        method: GET\n        description: An organization\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username (slug) of the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-username-users\n      path: /organizations/{username}/users\n      operations:\n      - name: getorgusers\n        method: GET\n        description: Organization's users\n        inputParameters:\n       \
  \ - name: username\n          in: path\n          type: string\n          required: true\n          description: The username (slug) of the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-username-articles\n      path: /organizations/{username}/articles\n      operations:\n      - name: getorgarticles\n        method: GET\n        description: Organization's Articles\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username (slug) of the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages\n      path: /pages\n      operations:\n      - name: getpages\n        method: GET\n        description: Show details for all pages\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createpage\n        method: POST\n        description: Create a new page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages-id\n      path: /pages/{id}\n      operations:\n      - name: getpagebyid\n        method: GET\n        description: Show details for a page\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepage\n        method: PUT\n        description: Update details for a page\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the page.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepage\n        method: DELETE\n        description: Remove a page\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: podcast-episodes\n      path: /podcast_episodes\n      operations:\n      - name: getpodcastepisodes\n        method: GET\n        description: Podcast Episodes\n        inputParameters:\n        - name: username\n          in: query\n          type: string\n          description: Filter podcast episodes by the podcast owner's username.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profile-images-username\n     \
  \ path: /profile_images/{username}\n      operations:\n      - name: getprofileimage\n        method: GET\n        description: A Users or organizations profile image\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username of the user or organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reactions-toggle\n      path: /reactions/toggle\n      operations:\n      - name: togglereaction\n        method: POST\n        description: Toggle reaction\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: true\n          description: The category of reaction.\n        - name: reactable_id\n          in: query\n          type: integer\n          required: true\n          description: The ID of the reactable entity.\n        - name:\
  \ reactable_type\n          in: query\n          type: string\n          required: true\n          description: The type of entity being reacted to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reactions\n      path: /reactions\n      operations:\n      - name: createreaction\n        method: POST\n        description: Create reaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: readinglist\n      path: /readinglist\n      operations:\n      - name: getreadinglist\n        method: GET\n        description: Readinglist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      operations:\n      - name: gettags\n        method: GET\n        description: Tags\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-me\n      path: /users/me\n      operations:\n      - name: getuserme\n        method: GET\n        description: The authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: A User\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id-unpublish\n      path: /users/{id}/unpublish\n      operations:\n      - name: unpublishuser\n        method: PUT\n        description: Unpublish a User's Articles and Comments\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id-suspend\n      path: /users/{id}/suspend\n      operations:\n      - name: suspenduser\n        method: PUT\n        description: Suspend a User\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: getwebhooks\n        method: GET\n        description: Webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: createwebhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-id\n      path: /webhooks/{id}\n      operations:\n      - name: getwebhookbyid\n        method: GET\n        description: A webhook endpoint\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhook\n        method: DELETE\n        description: Delete a webhook endpoint\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the webhook.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dev-to-rest\n    description: REST adapter for Dev.to Forem API.\n    resources:\n    - path: /articles\n      name: createarticle\n      operations:\n      - method: POST\n        name: createarticle\n        description: Publish article\n        call: dev-to.createarticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles\n      name: getarticles\n      operations:\n      - method: GET\n        name: getarticles\n        description: Published articles\n        call: dev-to.getarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/latest\n      name: getlatestarticles\n      operations:\n      - method: GET\n        name: getlatestarticles\n        description: Published articles sorted by published date\n        call: dev-to.getlatestarticles\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /articles/{id}\n      name: getarticlebyid\n      operations:\n      - method: GET\n        name: getarticlebyid\n        description: Published article by id\n        call: dev-to.getarticlebyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/{id}\n      name: updatearticle\n      operations:\n      - method: PUT\n        name: updatearticle\n        description: Update an article by id\n        call: dev-to.updatearticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/{username}/{slug}\n      name: getarticlebypath\n      operations:\n      - method: GET\n        name: getarticlebypath\n        description: Published article by path\n        call: dev-to.getarticlebypath\n        with:\n          username: rest.username\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /articles/me\n      name: getuserarticles\n      operations:\n      - method: GET\n        name: getuserarticles\n        description: User's articles\n        call: dev-to.getuserarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/me/published\n      name: getuserpublishedarticles\n      operations:\n      - method: GET\n        name: getuserpublishedarticles\n        description: User's published articles\n        call: dev-to.getuserpublishedarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/me/unpublished\n      name: getuserunpublishedarticles\n      operations:\n      - method: GET\n        name: getuserunpublishedarticles\n        description: User's unpublished articles\n        call: dev-to.getuserunpublishedarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/me/all\n      name: getuserallarticles\n      operations:\n\
  \      - method: GET\n        name: getuserallarticles\n        description: User's all articles\n        call: dev-to.getuserallarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles/{id}/unpublish\n      name: unpublisharticle\n      operations:\n      - method: PUT\n        name: unpublisharticle\n        description: Unpublish an article\n        call: dev-to.unpublisharticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments\n      name: getcommentsbyarticleid\n      operations:\n      - method: GET\n        name: getcommentsbyarticleid\n        description: Comments\n        call: dev-to.getcommentsbyarticleid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/{id}\n      name: getcommentbyid\n      operations:\n      - method: GET\n        name: getcommentbyid\n        description: Comment by id\n        call: dev-to.getcommentbyid\n    \
  \    with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /display_ads\n      name: getdisplayads\n      operations:\n      - method: GET\n        name: getdisplayads\n        description: Display ads\n        call: dev-to.getdisplayads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /display_ads\n      name: createdisplayad\n      operations:\n      - method: POST\n        name: createdisplayad\n        description: Create display ad\n        call: dev-to.createdisplayad\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /display_ads/{id}\n      name: getdisplayadbyid\n      operations:\n      - method: GET\n        name: getdisplayadbyid\n        description: Display ad\n        call: dev-to.getdisplayadbyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /display_ads/{id}\n\
  \      name: updatedisplayad\n      operations:\n      - method: PUT\n        name: updatedisplayad\n        description: Update display ad\n        call: dev-to.updatedisplayad\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /display_ads/{id}/unpublish\n      name: unpublishdisplayad\n      operations:\n      - method: PUT\n        name: unpublishdisplayad\n        description: Unpublish display ad\n        call: dev-to.unpublishdisplayad\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /follows/tags\n      name: getfollowedtags\n      operations:\n      - method: GET\n        name: getfollowedtags\n        description: Followed Tags\n        call: dev-to.getfollowedtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /followers/users\n      name: getfollowers\n      operations:\n      - method:\
  \ GET\n        name: getfollowers\n        description: Followers\n        call: dev-to.getfollowers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{username}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: An organization\n        call: dev-to.getorganization\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{username}/users\n      name: getorgusers\n      operations:\n      - method: GET\n        name: getorgusers\n        description: Organization's users\n        call: dev-to.getorgusers\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{username}/articles\n      name: getorgarticles\n      operations:\n      - method: GET\n        name: getorgarticles\n\
  \        description: Organization's Articles\n        call: dev-to.getorgarticles\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages\n      name: getpages\n      operations:\n      - method: GET\n        name: getpages\n        description: Show details for all pages\n        call: dev-to.getpages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages\n      name: createpage\n      operations:\n      - method: POST\n        name: createpage\n        description: Create a new page\n        call: dev-to.createpage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{id}\n      name: getpagebyid\n      operations:\n      - method: GET\n        name: getpagebyid\n        description: Show details for a page\n        call: dev-to.getpagebyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /pages/{id}\n      name: updatepage\n      operations:\n      - method: PUT\n        name: updatepage\n        description: Update details for a page\n        call: dev-to.updatepage\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{id}\n      name: deletepage\n      operations:\n      - method: DELETE\n        name: deletepage\n        description: Remove a page\n        call: dev-to.deletepage\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /podcast_episodes\n      name: getpodcastepisodes\n      operations:\n      - method: GET\n        name: getpodcastepisodes\n        description: Podcast Episodes\n        call: dev-to.getpodcastepisodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /profile_images/{username}\n      name: getprofileimage\n\
  \      operations:\n      - method: GET\n        name: getprofileimage\n        description: A Users or organizations profile image\n        call: dev-to.getprofileimage\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reactions/toggle\n      name: togglereaction\n      operations:\n      - method: POST\n        name: togglereaction\n        description: Toggle reaction\n        call: dev-to.togglereaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reactions\n      name: createreaction\n      operations:\n      - method: POST\n        name: createreaction\n        description: Create reaction\n        call: dev-to.createreaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /readinglist\n      name: getreadinglist\n      operations:\n      - method: GET\n        name: getreadinglist\n        description: Readinglist\n\
  \        call: dev-to.getreadinglist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags\n      name: gettags\n      operations:\n      - method: GET\n        name: gettags\n        description: Tags\n        call: dev-to.gettags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me\n      name: getuserme\n      operations:\n      - method: GET\n        name: getuserme\n        description: The authenticated user\n        call: dev-to.getuserme\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: A User\n        call: dev-to.getuser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}/unpublish\n      name: unpublishuser\n      operations:\n      - method: PUT\n        name:\
  \ unpublishuser\n        description: Unpublish a User's Articles and Comments\n        call: dev-to.unpublishuser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}/suspend\n      name: suspenduser\n      operations:\n      - method: PUT\n        name: suspenduser\n        description: Suspend a User\n        call: dev-to.suspenduser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: getwebhooks\n      operations:\n      - method: GET\n        name: getwebhooks\n        description: Webhooks\n        call: dev-to.getwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Create a webhook\n        call: dev-to.createwebhook\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /webhooks/{id}\n      name: getwebhookbyid\n      operations:\n      - method: GET\n        name: getwebhookbyid\n        description: A webhook endpoint\n        call: dev-to.getwebhookbyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}\n      name: deletewebhook\n      operations:\n      - method: DELETE\n        name: deletewebhook\n        description: Delete a webhook endpoint\n        call: dev-to.deletewebhook\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: dev-to-mcp\n    transport: http\n    description: MCP adapter for Dev.to Forem API for AI agent use.\n    tools:\n    - name: createarticle\n      description: Publish article\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: dev-to.createarticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getarticles\n      description: Published articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dev-to.getarticles\n      with:\n        tag: tools.tag\n        tags: tools.tags\n        tags_exclude: tools.tags_exclude\n        username: tools.username\n        state: tools.state\n        top: tools.top\n        collection_id: tools.collection_id\n      inputParameters:\n      - name: tag\n        type: string\n        description: Filter articles by a single tag name.\n      - name: tags\n        type: string\n        description: Filter articles by a comma-separated list of tag names (articles must have all specified tags).\n      - name: tags_exclude\n        type: string\n        description: Exclude articles with these comma-separated tag names.\n      - name: username\n        type: string\n        description:\
  \ Filter articles by the author's username.\n      - name: state\n        type: string\n        description: Filter articles by state. Defaults to the most popular articles.\n      - name: top\n        type: integer\n        description: Return the most popular articles published in the last N days.\n      - name: collection_id\n        type: integer\n        description: Return articles belonging to the specified collection.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlatestarticles\n      description: Published articles sorted by published date\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dev-to.getlatestarticles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getarticlebyid\n      description: Published article by id\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dev-to.getarticlebyid\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: updatearticle\n      description: Update an article by id\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: dev-to.updatearticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getarticlebypath\n      description: Published article by path\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dev-to.getarticlebypath\n      with:\n        username: tools.username\n        slug: tools.slug\n      inputParameters:\n      - name: username\n        type: string\n        description: The username of the article's author.\n        required: true\n      - name: slug\n        type: string\n        description: The slug of the article.\n        required: true\n      outputParameter\n\n# --- truncated at 32 KB (44 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/dev-to/refs/heads/main/capabilities/dev-to-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dev-to/refs/heads/main/capabilities/dev-to-capability.yaml
tags:
- Dev
- To
- API
tools:
- description: Publish article
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createarticle
- description: Published articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarticles
- description: Published articles sorted by published date
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatestarticles
- description: Published article by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarticlebyid
- description: Update an article by id
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatearticle
- description: Published article by path
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarticlebypath
- description: User's articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserarticles
- description: User's published articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserpublishedarticles
- description: User's unpublished articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserunpublishedarticles
- description: User's all articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserallarticles
- description: Unpublish an article
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unpublisharticle
- description: Comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommentsbyarticleid
- description: Comment by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommentbyid
- description: Display ads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdisplayads
- description: Create display ad
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdisplayad
- description: Display ad
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdisplayadbyid
- description: Update display ad
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedisplayad
- description: Unpublish display ad
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unpublishdisplayad
- description: Followed Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfollowedtags
- description: Followers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfollowers
- description: An organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: Organization's users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorgusers
- description: Organization's Articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorgarticles
- description: Show details for all pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpages
- description: Create a new page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpage
- description: Show details for a page
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpagebyid
- description: Update details for a page
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepage
- description: Remove a page
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepage
- description: Podcast Episodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpodcastepisodes
- description: A Users or organizations profile image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofileimage
- description: Toggle reaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: togglereaction
- description: Create reaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreaction
- description: Readinglist
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreadinglist
- description: Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettags
- description: The authenticated user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserme
- description: A User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Unpublish a User's Articles and Comments
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unpublishuser
- description: Suspend a User
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspenduser
- description: Webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhooks
- description: Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: A webhook endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhookbyid
- description: Delete a webhook endpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhook
---
