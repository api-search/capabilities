---
categories: []
consumed_apis: []
description: The Ghost Admin API provides full read and write access to all content and configuration within a Ghost publication. It enables developers to create, update, and delete posts, pages, tags, members, tiers, newsletters, and offers programmatically. Authentication is handled via JSON Web Tokens generated from an Admin API key, integration tokens, or staff access tokens. The Admin API supports everything the Ghost Admin interface can do and more, making it suitable for building custom publishing workflows, content automation, member management systems, and advanced integrations.
layout: capability
name: Ghost Admin API
operations:
- description: Browse posts
  method: GET
  name: adminbrowseposts
  path: /posts/
- description: Create a post
  method: POST
  name: admincreatepost
  path: /posts/
- description: Read a post by ID
  method: GET
  name: adminreadpost
  path: /posts/{id}/
- description: Update a post
  method: PUT
  name: adminupdatepost
  path: /posts/{id}/
- description: Delete a post
  method: DELETE
  name: admindeletepost
  path: /posts/{id}/
- description: Browse pages
  method: GET
  name: adminbrowsepages
  path: /pages/
- description: Create a page
  method: POST
  name: admincreatepage
  path: /pages/
- description: Read a page by ID
  method: GET
  name: adminreadpage
  path: /pages/{id}/
- description: Update a page
  method: PUT
  name: adminupdatepage
  path: /pages/{id}/
- description: Delete a page
  method: DELETE
  name: admindeletepage
  path: /pages/{id}/
- description: Browse tags
  method: GET
  name: adminbrowsetags
  path: /tags/
- description: Create a tag
  method: POST
  name: admincreatetag
  path: /tags/
- description: Read a tag by ID
  method: GET
  name: adminreadtag
  path: /tags/{id}/
- description: Update a tag
  method: PUT
  name: adminupdatetag
  path: /tags/{id}/
- description: Delete a tag
  method: DELETE
  name: admindeletetag
  path: /tags/{id}/
- description: Browse members
  method: GET
  name: adminbrowsemembers
  path: /members/
- description: Create a member
  method: POST
  name: admincreatemember
  path: /members/
- description: Read a member by ID
  method: GET
  name: adminreadmember
  path: /members/{id}/
- description: Update a member
  method: PUT
  name: adminupdatemember
  path: /members/{id}/
- description: Delete a member
  method: DELETE
  name: admindeletemember
  path: /members/{id}/
- description: Browse tiers
  method: GET
  name: adminbrowsetiers
  path: /tiers/
- description: Create a tier
  method: POST
  name: admincreatetier
  path: /tiers/
- description: Read a tier by ID
  method: GET
  name: adminreadtier
  path: /tiers/{id}/
- description: Update a tier
  method: PUT
  name: adminupdatetier
  path: /tiers/{id}/
- description: Browse newsletters
  method: GET
  name: adminbrowsenewsletters
  path: /newsletters/
- description: Create a newsletter
  method: POST
  name: admincreatenewsletter
  path: /newsletters/
- description: Read a newsletter by ID
  method: GET
  name: adminreadnewsletter
  path: /newsletters/{id}/
- description: Update a newsletter
  method: PUT
  name: adminupdatenewsletter
  path: /newsletters/{id}/
- description: Browse offers
  method: GET
  name: adminbrowseoffers
  path: /offers/
- description: Create an offer
  method: POST
  name: admincreateoffer
  path: /offers/
- description: Read an offer by ID
  method: GET
  name: adminreadoffer
  path: /offers/{id}/
- description: Update an offer
  method: PUT
  name: adminupdateoffer
  path: /offers/{id}/
- description: Browse users
  method: GET
  name: adminbrowseusers
  path: /users/
- description: Read a user by ID
  method: GET
  name: adminreaduser
  path: /users/{id}/
- description: Create a webhook
  method: POST
  name: admincreatewebhook
  path: /webhooks/
- description: Update a webhook
  method: PUT
  name: adminupdatewebhook
  path: /webhooks/{id}/
- description: Delete a webhook
  method: DELETE
  name: admindeletewebhook
  path: /webhooks/{id}/
- description: Upload an image
  method: POST
  name: adminuploadimage
  path: /images/upload/
- description: Upload a theme
  method: POST
  name: adminuploadtheme
  path: /themes/upload/
- description: Activate a theme
  method: PUT
  name: adminactivatetheme
  path: /themes/{name}/activate/
- description: Read site information
  method: GET
  name: adminreadsite
  path: /site/
personas: []
provider_name: Ghost
provider_slug: ghost
search_terms:
- adminreadtier
- adminreadnewsletter
- update a post
- create an offer
- api
- adminreadtag
- adminupdatepage
- admindeletemember
- update a member
- activate a theme
- admindeletepost
- admincreatepage
- create a member
- adminupdatepost
- delete a page
- memberships
- upload a theme
- create a webhook
- adminreadpage
- adminbrowsetiers
- newsletters
- read a tier by id
- adminbrowsepages
- admincreatetier
- adminreadsite
- read an offer by id
- headless cms
- adminreadmember
- adminreaduser
- adminupdatetag
- read a post by id
- adminactivatetheme
- admincreatepost
- publishing
- adminbrowseposts
- admincreatetag
- update an offer
- read a user by id
- ghost
- read a newsletter by id
- admincreatenewsletter
- create a newsletter
- adminreadpost
- update a tag
- read site information
- create a tag
- adminbrowsenewsletters
- delete a tag
- delete a webhook
- browse members
- delete a member
- read a tag by id
- browse pages
- read a page by id
- adminbrowsetags
- adminupdateoffer
- browse tags
- update a newsletter
- browse offers
- create a page
- adminbrowsemembers
- browse newsletters
- admindeletepage
- admincreatewebhook
- create a tier
- create a post
- adminbrowseusers
- admindeletetag
- browse posts
- admincreatemember
- adminupdatenewsletter
- update a tier
- admincreateoffer
- adminupdatewebhook
- browse tiers
- adminreadoffer
- browse users
- blogging
- admindeletewebhook
- adminupdatetier
- read a member by id
- update a page
- delete a post
- adminuploadimage
- upload an image
- adminbrowseoffers
- content management
- adminuploadtheme
- update a webhook
- adminupdatemember
slug: ghost-capability
source_filename: ghost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ghost Admin API\n  description: The Ghost Admin API provides full read and write access to all content and configuration within a Ghost publication.\n    It enables developers to create, update, and delete posts, pages, tags, members, tiers, newsletters, and offers programmatically.\n    Authentication is handled via JSON Web Tokens generated from an Admin API key, integration tokens, or staff access tokens.\n    The Admin API supports everything the Ghost Admin interface can do and more, making it suitable for building custom publishing\n    workflows, content automation, member management systems, and advanced integrations.\n  tags:\n  - Ghost\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ghost\n    baseUri: https://your-site.ghost.io/ghost/api/admin\n    description: Ghost Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GHOST_TOKEN}}'\n\
  \    resources:\n    - name: posts\n      path: /posts/\n      operations:\n      - name: adminbrowseposts\n        method: GET\n        description: Browse posts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreatepost\n        method: POST\n        description: Create a post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posts-id\n      path: /posts/{id}/\n      operations:\n      - name: adminreadpost\n        method: GET\n        description: Read a post by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adminupdatepost\n        method: PUT\n        description: Update a post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: admindeletepost\n        method: DELETE\n        description: Delete a post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages\n      path: /pages/\n      operations:\n      - name: adminbrowsepages\n        method: GET\n        description: Browse pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreatepage\n        method: POST\n        description: Create a page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages-id\n      path: /pages/{id}/\n      operations:\n      - name: adminreadpage\n        method: GET\n        description: Read a page by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: adminupdatepage\n        method: PUT\n        description: Update a page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admindeletepage\n        method: DELETE\n        description: Delete a page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags/\n      operations:\n      - name: adminbrowsetags\n        method: GET\n        description: Browse tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreatetag\n        method: POST\n        description: Create a tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-id\n      path: /tags/{id}/\n      operations:\n      - name: adminreadtag\n\
  \        method: GET\n        description: Read a tag by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adminupdatetag\n        method: PUT\n        description: Update a tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admindeletetag\n        method: DELETE\n        description: Delete a tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /members/\n      operations:\n      - name: adminbrowsemembers\n        method: GET\n        description: Browse members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreatemember\n        method: POST\n        description: Create a member\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members-id\n      path: /members/{id}/\n      operations:\n      - name: adminreadmember\n        method: GET\n        description: Read a member by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adminupdatemember\n        method: PUT\n        description: Update a member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admindeletemember\n        method: DELETE\n        description: Delete a member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tiers\n      path: /tiers/\n      operations:\n      - name: adminbrowsetiers\n        method: GET\n        description: Browse tiers\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreatetier\n        method: POST\n        description: Create a tier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tiers-id\n      path: /tiers/{id}/\n      operations:\n      - name: adminreadtier\n        method: GET\n        description: Read a tier by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adminupdatetier\n        method: PUT\n        description: Update a tier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: newsletters\n      path: /newsletters/\n      operations:\n      - name: adminbrowsenewsletters\n        method: GET\n        description: Browse\
  \ newsletters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreatenewsletter\n        method: POST\n        description: Create a newsletter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: newsletters-id\n      path: /newsletters/{id}/\n      operations:\n      - name: adminreadnewsletter\n        method: GET\n        description: Read a newsletter by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adminupdatenewsletter\n        method: PUT\n        description: Update a newsletter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers\n      path: /offers/\n      operations:\n      - name: adminbrowseoffers\n\
  \        method: GET\n        description: Browse offers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admincreateoffer\n        method: POST\n        description: Create an offer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers-id\n      path: /offers/{id}/\n      operations:\n      - name: adminreadoffer\n        method: GET\n        description: Read an offer by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adminupdateoffer\n        method: PUT\n        description: Update an offer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users/\n      operations:\n      - name: adminbrowseusers\n\
  \        method: GET\n        description: Browse users\n        inputParameters:\n        - name: include\n          in: query\n          type: string\n          description: Include related resources. Supports count.posts and roles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}/\n      operations:\n      - name: adminreaduser\n        method: GET\n        description: Read a user by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks/\n      operations:\n      - name: admincreatewebhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-id\n      path: /webhooks/{id}/\n      operations:\n\
  \      - name: adminupdatewebhook\n        method: PUT\n        description: Update a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: admindeletewebhook\n        method: DELETE\n        description: Delete a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-upload\n      path: /images/upload/\n      operations:\n      - name: adminuploadimage\n        method: POST\n        description: Upload an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: themes-upload\n      path: /themes/upload/\n      operations:\n      - name: adminuploadtheme\n        method: POST\n        description: Upload a theme\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: themes-name-activate\n      path: /themes/{name}/activate/\n      operations:\n      - name: adminactivatetheme\n        method: PUT\n        description: Activate a theme\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the theme to activate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: site\n      path: /site/\n      operations:\n      - name: adminreadsite\n        method: GET\n        description: Read site information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ghost-rest\n    description: REST adapter for Ghost Admin API.\n    resources:\n    - path: /posts/\n      name: adminbrowseposts\n      operations:\n\
  \      - method: GET\n        name: adminbrowseposts\n        description: Browse posts\n        call: ghost.adminbrowseposts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /posts/\n      name: admincreatepost\n      operations:\n      - method: POST\n        name: admincreatepost\n        description: Create a post\n        call: ghost.admincreatepost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /posts/{id}/\n      name: adminreadpost\n      operations:\n      - method: GET\n        name: adminreadpost\n        description: Read a post by ID\n        call: ghost.adminreadpost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /posts/{id}/\n      name: adminupdatepost\n      operations:\n      - method: PUT\n        name: adminupdatepost\n        description: Update a post\n        call: ghost.adminupdatepost\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /posts/{id}/\n      name: admindeletepost\n      operations:\n      - method: DELETE\n        name: admindeletepost\n        description: Delete a post\n        call: ghost.admindeletepost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/\n      name: adminbrowsepages\n      operations:\n      - method: GET\n        name: adminbrowsepages\n        description: Browse pages\n        call: ghost.adminbrowsepages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/\n      name: admincreatepage\n      operations:\n      - method: POST\n        name: admincreatepage\n        description: Create a page\n        call: ghost.admincreatepage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{id}/\n      name: adminreadpage\n      operations:\n      - method: GET\n        name: adminreadpage\n        description: Read a page by ID\n      \
  \  call: ghost.adminreadpage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{id}/\n      name: adminupdatepage\n      operations:\n      - method: PUT\n        name: adminupdatepage\n        description: Update a page\n        call: ghost.adminupdatepage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{id}/\n      name: admindeletepage\n      operations:\n      - method: DELETE\n        name: admindeletepage\n        description: Delete a page\n        call: ghost.admindeletepage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/\n      name: adminbrowsetags\n      operations:\n      - method: GET\n        name: adminbrowsetags\n        description: Browse tags\n        call: ghost.adminbrowsetags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/\n      name: admincreatetag\n      operations:\n      - method:\
  \ POST\n        name: admincreatetag\n        description: Create a tag\n        call: ghost.admincreatetag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{id}/\n      name: adminreadtag\n      operations:\n      - method: GET\n        name: adminreadtag\n        description: Read a tag by ID\n        call: ghost.adminreadtag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{id}/\n      name: adminupdatetag\n      operations:\n      - method: PUT\n        name: adminupdatetag\n        description: Update a tag\n        call: ghost.adminupdatetag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{id}/\n      name: admindeletetag\n      operations:\n      - method: DELETE\n        name: admindeletetag\n        description: Delete a tag\n        call: ghost.admindeletetag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /members/\n      name: adminbrowsemembers\n      operations:\n      - method: GET\n        name: adminbrowsemembers\n        description: Browse members\n        call: ghost.adminbrowsemembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members/\n      name: admincreatemember\n      operations:\n      - method: POST\n        name: admincreatemember\n        description: Create a member\n        call: ghost.admincreatemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members/{id}/\n      name: adminreadmember\n      operations:\n      - method: GET\n        name: adminreadmember\n        description: Read a member by ID\n        call: ghost.adminreadmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members/{id}/\n      name: adminupdatemember\n      operations:\n      - method: PUT\n        name: adminupdatemember\n        description: Update a member\n\
  \        call: ghost.adminupdatemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members/{id}/\n      name: admindeletemember\n      operations:\n      - method: DELETE\n        name: admindeletemember\n        description: Delete a member\n        call: ghost.admindeletemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tiers/\n      name: adminbrowsetiers\n      operations:\n      - method: GET\n        name: adminbrowsetiers\n        description: Browse tiers\n        call: ghost.adminbrowsetiers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tiers/\n      name: admincreatetier\n      operations:\n      - method: POST\n        name: admincreatetier\n        description: Create a tier\n        call: ghost.admincreatetier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tiers/{id}/\n      name: adminreadtier\n      operations:\n\
  \      - method: GET\n        name: adminreadtier\n        description: Read a tier by ID\n        call: ghost.adminreadtier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tiers/{id}/\n      name: adminupdatetier\n      operations:\n      - method: PUT\n        name: adminupdatetier\n        description: Update a tier\n        call: ghost.adminupdatetier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /newsletters/\n      name: adminbrowsenewsletters\n      operations:\n      - method: GET\n        name: adminbrowsenewsletters\n        description: Browse newsletters\n        call: ghost.adminbrowsenewsletters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /newsletters/\n      name: admincreatenewsletter\n      operations:\n      - method: POST\n        name: admincreatenewsletter\n        description: Create a newsletter\n        call: ghost.admincreatenewsletter\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /newsletters/{id}/\n      name: adminreadnewsletter\n      operations:\n      - method: GET\n        name: adminreadnewsletter\n        description: Read a newsletter by ID\n        call: ghost.adminreadnewsletter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /newsletters/{id}/\n      name: adminupdatenewsletter\n      operations:\n      - method: PUT\n        name: adminupdatenewsletter\n        description: Update a newsletter\n        call: ghost.adminupdatenewsletter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offers/\n      name: adminbrowseoffers\n      operations:\n      - method: GET\n        name: adminbrowseoffers\n        description: Browse offers\n        call: ghost.adminbrowseoffers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offers/\n      name: admincreateoffer\n\
  \      operations:\n      - method: POST\n        name: admincreateoffer\n        description: Create an offer\n        call: ghost.admincreateoffer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offers/{id}/\n      name: adminreadoffer\n      operations:\n      - method: GET\n        name: adminreadoffer\n        description: Read an offer by ID\n        call: ghost.adminreadoffer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offers/{id}/\n      name: adminupdateoffer\n      operations:\n      - method: PUT\n        name: adminupdateoffer\n        description: Update an offer\n        call: ghost.adminupdateoffer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/\n      name: adminbrowseusers\n      operations:\n      - method: GET\n        name: adminbrowseusers\n        description: Browse users\n        call: ghost.adminbrowseusers\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /users/{id}/\n      name: adminreaduser\n      operations:\n      - method: GET\n        name: adminreaduser\n        description: Read a user by ID\n        call: ghost.adminreaduser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/\n      name: admincreatewebhook\n      operations:\n      - method: POST\n        name: admincreatewebhook\n        description: Create a webhook\n        call: ghost.admincreatewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}/\n      name: adminupdatewebhook\n      operations:\n      - method: PUT\n        name: adminupdatewebhook\n        description: Update a webhook\n        call: ghost.adminupdatewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}/\n      name: admindeletewebhook\n      operations:\n      - method: DELETE\n    \
  \    name: admindeletewebhook\n        description: Delete a webhook\n        call: ghost.admindeletewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/upload/\n      name: adminuploadimage\n      operations:\n      - method: POST\n        name: adminuploadimage\n        description: Upload an image\n        call: ghost.adminuploadimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /themes/upload/\n      name: adminuploadtheme\n      operations:\n      - method: POST\n        name: adminuploadtheme\n        description: Upload a theme\n        call: ghost.adminuploadtheme\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /themes/{name}/activate/\n      name: adminactivatetheme\n      operations:\n      - method: PUT\n        name: adminactivatetheme\n        description: Activate a theme\n        call: ghost.adminactivatetheme\n        with:\n          name:\
  \ rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /site/\n      name: adminreadsite\n      operations:\n      - method: GET\n        name: adminreadsite\n        description: Read site information\n        call: ghost.adminreadsite\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ghost-mcp\n    transport: http\n    description: MCP adapter for Ghost Admin API for AI agent use.\n    tools:\n    - name: adminbrowseposts\n      description: Browse posts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminbrowseposts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreatepost\n      description: Create a post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatepost\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: adminreadpost\n      description: Read a post by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadpost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatepost\n      description: Update a post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ghost.adminupdatepost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admindeletepost\n      description: Delete a post\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ghost.admindeletepost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowsepages\n      description: Browse pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminbrowsepages\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreatepage\n      description: Create a page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatepage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreadpage\n      description: Read a page by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadpage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatepage\n      description: Update a page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ghost.adminupdatepage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admindeletepage\n      description: Delete a page\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n\
  \      call: ghost.admindeletepage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowsetags\n      description: Browse tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminbrowsetags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreatetag\n      description: Create a tag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatetag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreadtag\n      description: Read a tag by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadtag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatetag\n      description: Update a tag\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: ghost.adminupdatetag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admindeletetag\n      description: Delete a tag\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ghost.admindeletetag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowsemembers\n      description: Browse members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminbrowsemembers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreatemember\n      description: Create a member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreadmember\n      description: Read a member by ID\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadmember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatemember\n      description: Update a member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ghost.adminupdatemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admindeletemember\n      description: Delete a member\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ghost.admindeletemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowsetiers\n      description: Browse tiers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminbrowsetiers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreatetier\n \
  \     description: Create a tier\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatetier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreadtier\n      description: Read a tier by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadtier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatetier\n      description: Update a tier\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ghost.adminupdatetier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowsenewsletters\n      description: Browse newsletters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminbrowsenewsletters\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: admincreatenewsletter\n      description: Create a newsletter\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatenewsletter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreadnewsletter\n      description: Read a newsletter by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadnewsletter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatenewsletter\n      description: Update a newsletter\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ghost.adminupdatenewsletter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowseoffers\n      description: Browse offers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: ghost.adminbrowseoffers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreateoffer\n      description: Create an offer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreateoffer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreadoffer\n      description: Read an offer by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreadoffer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdateoffer\n      description: Update an offer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ghost.adminupdateoffer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminbrowseusers\n      description: Browse users\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: ghost.adminbrowseusers\n      with:\n        include: tools.include\n      inputParameters:\n      - name: include\n        type: string\n        description: Include related resources. Supports count.posts and roles.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminreaduser\n      description: Read a user by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ghost.adminreaduser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admincreatewebhook\n      description: Create a webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.admincreatewebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminupdatewebhook\n      description: Update a webhook\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: ghost.adminupdatewebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: admindeletewebhook\n      description: Delete a webhook\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ghost.admindeletewebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminuploadimage\n      description: Upload an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.adminuploadimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminuploadtheme\n      description: Upload a theme\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ghost.adminuploadtheme\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adminactivatetheme\n      description: Activate a th\n\
  \n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/ghost/refs/heads/main/capabilities/ghost-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ghost/refs/heads/main/capabilities/ghost-capability.yaml
tags:
- Ghost
- API
tools:
- description: Browse posts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowseposts
- description: Create a post
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatepost
- description: Read a post by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadpost
- description: Update a post
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatepost
- description: Delete a post
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: admindeletepost
- description: Browse pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowsepages
- description: Create a page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatepage
- description: Read a page by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadpage
- description: Update a page
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatepage
- description: Delete a page
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: admindeletepage
- description: Browse tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowsetags
- description: Create a tag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatetag
- description: Read a tag by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadtag
- description: Update a tag
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatetag
- description: Delete a tag
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: admindeletetag
- description: Browse members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowsemembers
- description: Create a member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatemember
- description: Read a member by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadmember
- description: Update a member
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatemember
- description: Delete a member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: admindeletemember
- description: Browse tiers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowsetiers
- description: Create a tier
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatetier
- description: Read a tier by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadtier
- description: Update a tier
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatetier
- description: Browse newsletters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowsenewsletters
- description: Create a newsletter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatenewsletter
- description: Read a newsletter by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadnewsletter
- description: Update a newsletter
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatenewsletter
- description: Browse offers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowseoffers
- description: Create an offer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreateoffer
- description: Read an offer by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadoffer
- description: Update an offer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdateoffer
- description: Browse users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminbrowseusers
- description: Read a user by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreaduser
- description: Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreatewebhook
- description: Update a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminupdatewebhook
- description: Delete a webhook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: admindeletewebhook
- description: Upload an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adminuploadimage
- description: Upload a theme
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adminuploadtheme
- description: Activate a theme
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adminactivatetheme
- description: Read site information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: adminreadsite
---
