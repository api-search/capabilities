---
categories:
- content-management
consumed_apis: []
description: Content creation and management workflow for blog posts, authors, pages, domains, and source code.
layout: capability
name: HubSpot Content Management
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- getsourcecodemetadata
- scheduleblogpost
- createblogpost
- hubspot list all blog authors
- listsitepages
- hubspot push draft to live
- hubspot clone a blog post
- getblogpostbyid
- detachblogpostfromlanguagegroup
- hubspot get a hubdb table
- hubspot delete a hubdb table
- hubspot set new primary language
- attachblogposttolanguagegroup
- hubspot extract a zip archive
- listhubdbtables
- publishhubdbtabledraft
- createblogauthor
- deletehubdbtablerow
- hubspot attach post to language group
- updateblogauthor
- extractzipfileasync
- hubspot get extraction task status
- archiveblogpost
- hubspot create a hubdb table
- getblogauthorbyid
- customer service
- gethubdbtablerow
- listdomains
- hubspot delete a source code file
- hubspot update a site page
- hubspot detach post from language group
- hubspot list hubdb table rows
- attachblogauthortolanguagegroup
- hubspot read multiple blog posts
- hubspot update a blog author
- setnewblogauthorlanguageprimary
- createhubdbtable
- createlandingpage
- downloadsourcecodefile
- hubspot list all blog posts
- hubspot update multiple blog posts
- batcharchiveblogposts
- validatesourcecodefile
- addhubdbtablerow
- updatehubdbtablerow
- batchcreateblogposts
- hubspot get a site page
- updateblogpost
- hubspot list hubdb tables
- hubspot archive multiple blog posts
- batchreadblogposts
- createsitepage
- hubspot publish hubdb table draft
- gethubdbtable
- batchupdateblogposts
- marketing
- getsitepage
- hubspot list site pages
- deletelandingpage
- hubspot read multiple blog authors
- restoreblogpostrevision
- deletesitepage
- listhubdbtablerows
- batchupdateblogauthors
- hubspot get revision history
- batchcreateblogauthors
- hubspot delete a site page
- archiveblogauthor
- hubspot create a blog author
- listblogposts
- hubspot archive multiple blog authors
- hubspot delete a hubdb table row
- listblogauthors
- hubspot detach author from language group
- hubspot list all domains
- batchreadblogauthors
- hubspot download a source code file
- detachblogauthorfromlanguagegroup
- cloneblogpost
- deletesourcecodefile
- hubspot create multiple blog posts
- content
- hubspot retrieve file or folder metadata
- hubspot archive a blog author
- hubspot get a domain by id
- hubspot create language variation
- createblogauthorlanguagevariation
- createblogpostlanguagevariation
- updatesitepage
- hubspot retrieve a blog author
- deletehubdbtable
- hubspot update a hubdb table row
- publishsitepage
- updatehubdbtable
- hubspot schedule a blog post
- hubspot reset draft to live version
- hubspot create a blog post
- hubspot retrieve a blog post
- hubspot create multiple blog authors
- hubspot list landing pages
- commerce
- hubspot archive a blog post
- email marketing
- analytics
- hubspot
- operations
- hubspot attach author to language group
- hubspot get a landing page
- resetblogpostdraft
- hubspot publish a site page
- blogs
- getdomainbyid
- upsertsourcecodefile
- setblogpostlanguageprimary
- hubspot create a site page
- hubspot add a row to a hubdb table
- getlandingpage
- listlandingpages
- getextractiontaskstatus
- crm
- cms
- hubspot validate a source code file
- hubspot get a hubdb table row
- hubspot create a new source code file
- hubspot create or update a source code file
- hubspot update multiple blog authors
- pushblogpostdraftlive
- hubspot create a landing page
- sales
- hubspot restore a previous version
- getblogpostrevisions
- batcharchiveblogauthors
- hubspot delete a landing page
- hubspot update a hubdb table
- marketing automation
- hubspot update a blog post
- createsourcecodefile
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Content Management\n  description: Content creation and management workflow for blog posts, authors, pages, domains, and source code.\n  tags:\n  - HubSpot\n  - CMS\n  - Content\n  - Blogs\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: blog-posts-api\n    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Blog Posts API enables you to manage blog posts programmatically. \\nCreate, update, publish,\\\n      \\ and schedule blog posts, manage drafts and revisions, \\nhandle multi-language content, and perfor\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: posts\n      path: /posts\n      description: posts operations\n      operations:\n      - name: listblogposts\n        method: GET\n        description: HubSpot\
  \ List All Blog Posts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createblogpost\n        method: POST\n        description: HubSpot Create a Blog Post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getblogpostbyid\n        method: GET\n        description: HubSpot Retrieve a Blog Post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateblogpost\n        method: PATCH\n        description: HubSpot Update a Blog Post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archiveblogpost\n        method: DELETE\n        description: HubSpot Archive a Blog Post\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: schedule\n      path: /schedule\n      description: schedule operations\n      operations:\n      - name: scheduleblogpost\n        method: POST\n        description: HubSpot Schedule a Blog Post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clone\n      path: /clone\n      description: clone operations\n      operations:\n      - name: cloneblogpost\n        method: POST\n        description: HubSpot Clone a Blog Post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-live\n      path: /push-live\n      description: push-live operations\n      operations:\n      - name: pushblogpostdraftlive\n        method: POST\n        description: HubSpot Push Draft to Live\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: reset\n      path: /reset\n      description: reset operations\n      operations:\n      - name: resetblogpostdraft\n        method: POST\n        description: HubSpot Reset Draft to Live Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revisions\n      path: /revisions\n      description: revisions operations\n      operations:\n      - name: getblogpostrevisions\n        method: GET\n        description: HubSpot Get Revision History\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restore\n      path: /restore\n      description: restore operations\n      operations:\n      - name: restoreblogpostrevision\n        method: POST\n        description: HubSpot Restore a Previous Version\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadblogposts\n        method: POST\n        description: HubSpot Read Multiple Blog Posts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreateblogposts\n        method: POST\n        description: HubSpot Create Multiple Blog Posts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdateblogposts\n        method: POST\n        description: HubSpot Update Multiple Blog Posts\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchiveblogposts\n        method: POST\n        description: HubSpot Archive Multiple Blog Posts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: detach-from-lang-group\n      path: /detach-from-lang-group\n      description: detach-from-lang-group operations\n      operations:\n      - name: detachblogpostfromlanguagegroup\n        method: POST\n        description: HubSpot Detach Post from Language Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: set-new-lang-primary\n      path: /set-new-lang-primary\n      description: set-new-lang-primary operations\n      operations:\n      -\
  \ name: setblogpostlanguageprimary\n        method: PUT\n        description: HubSpot Set New Primary Language\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attach-to-lang-group\n      path: /attach-to-lang-group\n      description: attach-to-lang-group operations\n      operations:\n      - name: attachblogposttolanguagegroup\n        method: POST\n        description: HubSpot Attach Post to Language Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create-language-variation\n      path: /create-language-variation\n      description: create-language-variation operations\n      operations:\n      - name: createblogpostlanguagevariation\n        method: POST\n        description: HubSpot Create Language Variation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n  - type: http\n    namespace: authors-api\n    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Blog Authors API enables you to manage author information for your \\nblog posts. Create, update,\\\n      \\ retrieve, and delete blog author profiles, manage \\nmulti-language author groups, and perform\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: authors\n      path: /authors\n      description: authors operations\n      operations:\n      - name: listblogauthors\n        method: GET\n        description: HubSpot List All Blog Authors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createblogauthor\n        method: POST\n        description: HubSpot Create a Blog Author\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: getblogauthorbyid\n        method: GET\n        description: HubSpot Retrieve a Blog Author\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateblogauthor\n        method: PATCH\n        description: HubSpot Update a Blog Author\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archiveblogauthor\n        method: DELETE\n        description: HubSpot Archive a Blog Author\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadblogauthors\n        method: POST\n        description: HubSpot Read Multiple Blog Authors\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreateblogauthors\n        method: POST\n        description: HubSpot Create Multiple Blog Authors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdateblogauthors\n        method: POST\n        description: HubSpot Update Multiple Blog Authors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchiveblogauthors\n        method: POST\n        description: HubSpot Archive Multiple Blog Authors\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: detach-from-lang-group\n      path: /detach-from-lang-group\n      description: detach-from-lang-group operations\n      operations:\n      - name: detachblogauthorfromlanguagegroup\n        method: POST\n        description: HubSpot Detach Author from Language Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: set-new-lang-primary\n      path: /set-new-lang-primary\n      description: set-new-lang-primary operations\n      operations:\n      - name: setnewblogauthorlanguageprimary\n        method: PUT\n        description: HubSpot Set New Primary Language\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attach-to-lang-group\n      path: /attach-to-lang-group\n      description: attach-to-lang-group\
  \ operations\n      operations:\n      - name: attachblogauthortolanguagegroup\n        method: POST\n        description: HubSpot Attach Author to Language Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create-language-variation\n      path: /create-language-variation\n      description: create-language-variation operations\n      operations:\n      - name: createblogauthorlanguagevariation\n        method: POST\n        description: HubSpot Create Language Variation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cms-pages-api\n    baseUri: https://api.hubapi.com\n    description: The CMS Pages API provides endpoints for creating and managing site pages and landing pages hosted on HubSpot.\n      You can create, retrieve, update, publish, and delete both site pages and landing\
  \ pages p\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: site-pages\n      path: /site-pages\n      description: site-pages operations\n      operations:\n      - name: listsitepages\n        method: GET\n        description: HubSpot List Site Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsitepage\n        method: POST\n        description: HubSpot Create a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsitepage\n        method: GET\n        description: HubSpot Get a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitepage\n        method: PATCH\n        description: HubSpot Update a Site Page\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesitepage\n        method: DELETE\n        description: HubSpot Delete a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-live\n      path: /push-live\n      description: push-live operations\n      operations:\n      - name: publishsitepage\n        method: POST\n        description: HubSpot Publish a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: landing-pages\n      path: /landing-pages\n      description: landing-pages operations\n      operations:\n      - name: listlandingpages\n        method: GET\n        description: HubSpot List Landing Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: createlandingpage\n        method: POST\n        description: HubSpot Create a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getlandingpage\n        method: GET\n        description: HubSpot Get a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelandingpage\n        method: DELETE\n        description: HubSpot Delete a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cms-hubdb-api\n    baseUri: https://api.hubapi.com\n    description: The HubDB API allows you to create, update, and delete HubDB data tables and their rows. HubDB tables can\n      be used as data sources for dynamic CMS pages and are\
  \ available in both draft and published ve\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: tables\n      path: /tables\n      description: tables operations\n      operations:\n      - name: listhubdbtables\n        method: GET\n        description: HubSpot List HubDB Tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createhubdbtable\n        method: POST\n        description: HubSpot Create a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gethubdbtable\n        method: GET\n        description: HubSpot Get a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatehubdbtable\n        method: PUT\n        description: HubSpot\
  \ Update a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehubdbtable\n        method: DELETE\n        description: HubSpot Delete a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rows\n      path: /rows\n      description: rows operations\n      operations:\n      - name: listhubdbtablerows\n        method: GET\n        description: HubSpot List HubDB Table Rows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addhubdbtablerow\n        method: POST\n        description: HubSpot Add a Row to a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gethubdbtablerow\n        method: GET\n\
  \        description: HubSpot Get a HubDB Table Row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatehubdbtablerow\n        method: PATCH\n        description: HubSpot Update a HubDB Table Row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehubdbtablerow\n        method: DELETE\n        description: HubSpot Delete a HubDB Table Row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-live\n      path: /push-live\n      description: push-live operations\n      operations:\n      - name: publishhubdbtabledraft\n        method: POST\n        description: HubSpot Publish HubDB Table Draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n  - type: http\n    namespace: domains-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot CMS Domains API allows you to retrieve information about domains connected to a HubSpot CMS\n      site.\n\n\n      Use this API to:\n\n      - List all domains connected to your HubSpot account\n\n      - Get detailed info'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: domains\n      path: /domains\n      description: domains operations\n      operations:\n      - name: listdomains\n        method: GET\n        description: HubSpot List All Domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdomainbyid\n        method: GET\n        description: HubSpot Get a Domain by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  -\
  \ type: http\n    namespace: source-code-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot CMS Source Code API provides programmatic access to files in the CMS Developer File System.\n\n      Use these endpoints to manage HTML templates, CSS stylesheets, JavaScript files, modules, and ot'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: content\n      path: /content\n      description: content operations\n      operations:\n      - name: downloadsourcecodefile\n        method: GET\n        description: HubSpot Download a Source Code File\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsourcecodefile\n        method: POST\n        description: HubSpot Create a New Source Code File\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: upsertsourcecodefile\n        method: PUT\n        description: HubSpot Create or Update a Source Code File\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesourcecodefile\n        method: DELETE\n        description: HubSpot Delete a Source Code File\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata\n      path: /metadata\n      description: metadata operations\n      operations:\n      - name: getsourcecodemetadata\n        method: GET\n        description: HubSpot Retrieve File or Folder Metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: validate\n      path: /validate\n      description: validate operations\n      operations:\n      - name: validatesourcecodefile\n        method:\
  \ POST\n        description: HubSpot Validate a Source Code File\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: async\n      path: /async\n      description: async operations\n      operations:\n      - name: extractzipfileasync\n        method: POST\n        description: HubSpot Extract a Zip Archive\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /status\n      description: status operations\n      operations:\n      - name: getextractiontaskstatus\n        method: GET\n        description: HubSpot Get Extraction Task Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9091\n    namespace: content-management-mcp\n    transport: http\n    description: MCP server for\
  \ AI-assisted HubSpot Content Management.\n    tools:\n    - name: listblogposts\n      description: HubSpot List All Blog Posts\n      hints:\n        readOnly: true\n      call: blog-posts-api.listblogposts\n    - name: createblogpost\n      description: HubSpot Create a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.createblogpost\n    - name: getblogpostbyid\n      description: HubSpot Retrieve a Blog Post\n      hints:\n        readOnly: true\n      call: blog-posts-api.getblogpostbyid\n    - name: updateblogpost\n      description: HubSpot Update a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.updateblogpost\n    - name: archiveblogpost\n      description: HubSpot Archive a Blog Post\n      hints:\n        destructive: true\n      call: blog-posts-api.archiveblogpost\n    - name: scheduleblogpost\n      description: HubSpot Schedule a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.scheduleblogpost\n\
  \    - name: cloneblogpost\n      description: HubSpot Clone a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.cloneblogpost\n    - name: pushblogpostdraftlive\n      description: HubSpot Push Draft to Live\n      hints:\n        readOnly: false\n      call: blog-posts-api.pushblogpostdraftlive\n    - name: resetblogpostdraft\n      description: HubSpot Reset Draft to Live Version\n      hints:\n        readOnly: false\n      call: blog-posts-api.resetblogpostdraft\n    - name: getblogpostrevisions\n      description: HubSpot Get Revision History\n      hints:\n        readOnly: true\n      call: blog-posts-api.getblogpostrevisions\n    - name: restoreblogpostrevision\n      description: HubSpot Restore a Previous Version\n      hints:\n        readOnly: false\n      call: blog-posts-api.restoreblogpostrevision\n    - name: batchreadblogposts\n      description: HubSpot Read Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batchreadblogposts\n\
  \    - name: batchcreateblogposts\n      description: HubSpot Create Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batchcreateblogposts\n    - name: batchupdateblogposts\n      description: HubSpot Update Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batchupdateblogposts\n    - name: batcharchiveblogposts\n      description: HubSpot Archive Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batcharchiveblogposts\n    - name: detachblogpostfromlanguagegroup\n      description: HubSpot Detach Post from Language Group\n      hints:\n        readOnly: false\n      call: blog-posts-api.detachblogpostfromlanguagegroup\n    - name: setblogpostlanguageprimary\n      description: HubSpot Set New Primary Language\n      hints:\n        readOnly: false\n      call: blog-posts-api.setblogpostlanguageprimary\n    - name: attachblogposttolanguagegroup\n      description: HubSpot Attach\
  \ Post to Language Group\n      hints:\n        readOnly: false\n      call: blog-posts-api.attachblogposttolanguagegroup\n    - name: createblogpostlanguagevariation\n      description: HubSpot Create Language Variation\n      hints:\n        readOnly: false\n      call: blog-posts-api.createblogpostlanguagevariation\n    - name: listblogauthors\n      description: HubSpot List All Blog Authors\n      hints:\n        readOnly: true\n      call: authors-api.listblogauthors\n    - name: createblogauthor\n      description: HubSpot Create a Blog Author\n      hints:\n        readOnly: false\n      call: authors-api.createblogauthor\n    - name: getblogauthorbyid\n      description: HubSpot Retrieve a Blog Author\n      hints:\n        readOnly: true\n      call: authors-api.getblogauthorbyid\n    - name: updateblogauthor\n      description: HubSpot Update a Blog Author\n      hints:\n        readOnly: false\n      call: authors-api.updateblogauthor\n    - name: archiveblogauthor\n      description:\
  \ HubSpot Archive a Blog Author\n      hints:\n        destructive: true\n      call: authors-api.archiveblogauthor\n    - name: batchreadblogauthors\n      description: HubSpot Read Multiple Blog Authors\n      hints:\n        readOnly: false\n      call: authors-api.batchreadblogauthors\n    - name: batchcreateblogauthors\n      description: HubSpot Create Multiple Blog Authors\n      hints:\n        readOnly: false\n      call: authors-api.batchcreateblogauthors\n    - name: batchupdateblogauthors\n      description: HubSpot Update Multiple Blog Authors\n      hints:\n        readOnly: false\n      call: authors-api.batchupdateblogauthors\n    - name: batcharchiveblogauthors\n      description: HubSpot Archive Multiple Blog Authors\n      hints:\n        readOnly: false\n      call: authors-api.batcharchiveblogauthors\n    - name: detachblogauthorfromlanguagegroup\n      description: HubSpot Detach Author from Language Group\n      hints:\n        readOnly: false\n      call: authors-api.detachblogauthorfromlanguagegroup\n\
  \    - name: setnewblogauthorlanguageprimary\n      description: HubSpot Set New Primary Language\n      hints:\n        readOnly: false\n      call: authors-api.setnewblogauthorlanguageprimary\n    - name: attachblogauthortolanguagegroup\n      description: HubSpot Attach Author to Language Group\n      hints:\n        readOnly: false\n      call: authors-api.attachblogauthortolanguagegroup\n    - name: createblogauthorlanguagevariation\n      description: HubSpot Create Language Variation\n      hints:\n        readOnly: false\n      call: authors-api.createblogauthorlanguagevariation\n    - name: listsitepages\n      description: HubSpot List Site Pages\n      hints:\n        readOnly: true\n      call: cms-pages-api.listsitepages\n    - name: createsitepage\n      description: HubSpot Create a Site Page\n      hints:\n        readOnly: false\n      call: cms-pages-api.createsitepage\n    - name: getsitepage\n      description: HubSpot Get a Site Page\n      hints:\n        readOnly:\
  \ true\n      call: cms-pages-api.getsitepage\n    - name: updatesitepage\n      description: HubSpot Update a Site Page\n      hints:\n        readOnly: false\n      call: cms-pages-api.updatesitepage\n    - name: deletesitepage\n      description: HubSpot Delete a Site Page\n      hints:\n        destructive: true\n      call: cms-pages-api.deletesitepage\n    - name: publishsitepage\n      description: HubSpot Publish a Site Page\n      hints:\n        readOnly: false\n      call: cms-pages-api.publishsitepage\n    - name: listlandingpages\n      description: HubSpot List Landing Pages\n      hints:\n        readOnly: true\n      call: cms-pages-api.listlandingpages\n    - name: createlandingpage\n      description: HubSpot Create a Landing Page\n      hints:\n        readOnly: false\n      call: cms-pages-api.createlandingpage\n    - name: getlandingpage\n      description: HubSpot Get a Landing Page\n      hints:\n        readOnly: true\n      call: cms-pages-api.getlandingpage\n\
  \    - name: deletelandingpage\n      description: HubSpot Delete a Landing Page\n      hints:\n        destructive: true\n      call: cms-pages-api.deletelandingpage\n    - name: listhubdbtables\n      description: HubSpot List HubDB Tables\n      hints:\n        readOnly: true\n      call: cms-hubdb-api.listhubdbtables\n    - name: createhubdbtable\n      description: HubSpot Create a HubDB Table\n      hints:\n        readOnly: false\n      call: cms-hubdb-api.createhubdbtable\n    - name: gethubdbtable\n      description: HubSpot Get a HubDB Table\n      hints:\n        readOnly: true\n      call: cms-hubdb-api.gethubdbtable\n    - name: updatehubdbtable\n      description: HubSpot Update a HubDB Table\n      hints:\n        readOnly: false\n      call: cms-hubdb-api.updatehubdbtable\n    - name: deletehubdbtable\n      description: HubSpot Delete a HubDB Table\n      hints:\n        destructive: true\n      call: cms-hubdb-api.deletehubdbtable\n    - name: listhubdbtablerows\n   \
  \   description: HubSpot List HubDB Table Rows\n      hints:\n        readOnly: true\n      call: cms-hubdb-api.listhubdbtablerows\n    - name: addhubdbtablerow\n      description: HubSpot Add a Row to a HubDB Table\n      hints:\n        readOnly: false\n      call: cms-hubdb-api.addhubdbtablerow\n    - name: gethubdbtablerow\n      description: HubSpot Get a HubDB Table Row\n      hints:\n        readOnly: true\n      call: cms-hubdb-api.gethubdbtablerow\n    - name: updatehubdbtablerow\n      description: HubSpot Update a HubDB Table Row\n      hints:\n        readOnly: false\n      call: cms-hubdb-api.updatehubdbtablerow\n    - name: deletehubdbtablerow\n      description: HubSpot Delete a HubDB Table Row\n      hints:\n        destructive: true\n      call: cms-hubdb-api.deletehubdbtablerow\n    - name: publishhubdbtabledraft\n      description: HubSpot Publish HubDB Table Draft\n      hints:\n        readOnly: false\n      call: cms-hubdb-api.publishhubdbtabledraft\n    - name: listdomains\n\
  \      description: HubSpot List All Domains\n      hints:\n        readOnly: true\n      call: domains-api.listdomains\n    - name: getdomainbyid\n      description: HubSpot Get a Domain by ID\n      hints:\n        readOnly: true\n      call: domains-api.getdomainbyid\n    - name: downloadsourcecodefile\n      description: HubSpot Download a Source Code File\n      hints:\n        readOnly: true\n      call: source-code-api.downloadsourcecodefile\n    - name: createsourcecodefile\n      description: HubSpot Create a New Source Code File\n      hints:\n        readOnly: false\n      call: source-code-api.createsourcecodefile\n    - name: upsertsourcecodefile\n      description: HubSpot Create or Update a Source Code File\n      hints:\n        readOnly: false\n      call: source-code-api.upsertsourcecodefile\n    - name: deletesourcecodefile\n      description: HubSpot Delete a Source Code File\n      hints:\n        destructive: true\n      call: source-code-api.deletesourcecodefile\n\
  \    - name: getsourcecodemetadata\n      description: HubSpot Retrieve File or Folder Metadata\n      hints:\n        readOnly: true\n      call: source-code-api.getsourcecodemetadata\n    - name: validatesourcecodefile\n      description: HubSpot Validate a Source Code File\n      hints:\n        readOnly: false\n      call: source-code-api.validatesourcecodefile\n    - name: extractzipfileasync\n      description: HubSpot Extract a Zip Archive\n      hints:\n        readOnly: false\n      call: source-code-api.extractzipfileasync\n    - name: getextractiontaskstatus\n      description: HubSpot Get Extraction Task Status\n      hints:\n        readOnly: true\n      call: source-code-api.getextractiontaskstatus\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/content-management.yaml
tags:
- HubSpot
- CMS
- Content
- Blogs
tools:
- description: HubSpot List All Blog Posts
  hints:
    readOnly: true
  name: listblogposts
- description: HubSpot Create a Blog Post
  hints:
    readOnly: false
  name: createblogpost
- description: HubSpot Retrieve a Blog Post
  hints:
    readOnly: true
  name: getblogpostbyid
- description: HubSpot Update a Blog Post
  hints:
    readOnly: false
  name: updateblogpost
- description: HubSpot Archive a Blog Post
  hints:
    destructive: true
  name: archiveblogpost
- description: HubSpot Schedule a Blog Post
  hints:
    readOnly: false
  name: scheduleblogpost
- description: HubSpot Clone a Blog Post
  hints:
    readOnly: false
  name: cloneblogpost
- description: HubSpot Push Draft to Live
  hints:
    readOnly: false
  name: pushblogpostdraftlive
- description: HubSpot Reset Draft to Live Version
  hints:
    readOnly: false
  name: resetblogpostdraft
- description: HubSpot Get Revision History
  hints:
    readOnly: true
  name: getblogpostrevisions
- description: HubSpot Restore a Previous Version
  hints:
    readOnly: false
  name: restoreblogpostrevision
- description: HubSpot Read Multiple Blog Posts
  hints:
    readOnly: false
  name: batchreadblogposts
- description: HubSpot Create Multiple Blog Posts
  hints:
    readOnly: false
  name: batchcreateblogposts
- description: HubSpot Update Multiple Blog Posts
  hints:
    readOnly: false
  name: batchupdateblogposts
- description: HubSpot Archive Multiple Blog Posts
  hints:
    readOnly: false
  name: batcharchiveblogposts
- description: HubSpot Detach Post from Language Group
  hints:
    readOnly: false
  name: detachblogpostfromlanguagegroup
- description: HubSpot Set New Primary Language
  hints:
    readOnly: false
  name: setblogpostlanguageprimary
- description: HubSpot Attach Post to Language Group
  hints:
    readOnly: false
  name: attachblogposttolanguagegroup
- description: HubSpot Create Language Variation
  hints:
    readOnly: false
  name: createblogpostlanguagevariation
- description: HubSpot List All Blog Authors
  hints:
    readOnly: true
  name: listblogauthors
- description: HubSpot Create a Blog Author
  hints:
    readOnly: false
  name: createblogauthor
- description: HubSpot Retrieve a Blog Author
  hints:
    readOnly: true
  name: getblogauthorbyid
- description: HubSpot Update a Blog Author
  hints:
    readOnly: false
  name: updateblogauthor
- description: HubSpot Archive a Blog Author
  hints:
    destructive: true
  name: archiveblogauthor
- description: HubSpot Read Multiple Blog Authors
  hints:
    readOnly: false
  name: batchreadblogauthors
- description: HubSpot Create Multiple Blog Authors
  hints:
    readOnly: false
  name: batchcreateblogauthors
- description: HubSpot Update Multiple Blog Authors
  hints:
    readOnly: false
  name: batchupdateblogauthors
- description: HubSpot Archive Multiple Blog Authors
  hints:
    readOnly: false
  name: batcharchiveblogauthors
- description: HubSpot Detach Author from Language Group
  hints:
    readOnly: false
  name: detachblogauthorfromlanguagegroup
- description: HubSpot Set New Primary Language
  hints:
    readOnly: false
  name: setnewblogauthorlanguageprimary
- description: HubSpot Attach Author to Language Group
  hints:
    readOnly: false
  name: attachblogauthortolanguagegroup
- description: HubSpot Create Language Variation
  hints:
    readOnly: false
  name: createblogauthorlanguagevariation
- description: HubSpot List Site Pages
  hints:
    readOnly: true
  name: listsitepages
- description: HubSpot Create a Site Page
  hints:
    readOnly: false
  name: createsitepage
- description: HubSpot Get a Site Page
  hints:
    readOnly: true
  name: getsitepage
- description: HubSpot Update a Site Page
  hints:
    readOnly: false
  name: updatesitepage
- description: HubSpot Delete a Site Page
  hints:
    destructive: true
  name: deletesitepage
- description: HubSpot Publish a Site Page
  hints:
    readOnly: false
  name: publishsitepage
- description: HubSpot List Landing Pages
  hints:
    readOnly: true
  name: listlandingpages
- description: HubSpot Create a Landing Page
  hints:
    readOnly: false
  name: createlandingpage
- description: HubSpot Get a Landing Page
  hints:
    readOnly: true
  name: getlandingpage
- description: HubSpot Delete a Landing Page
  hints:
    destructive: true
  name: deletelandingpage
- description: HubSpot List HubDB Tables
  hints:
    readOnly: true
  name: listhubdbtables
- description: HubSpot Create a HubDB Table
  hints:
    readOnly: false
  name: createhubdbtable
- description: HubSpot Get a HubDB Table
  hints:
    readOnly: true
  name: gethubdbtable
- description: HubSpot Update a HubDB Table
  hints:
    readOnly: false
  name: updatehubdbtable
- description: HubSpot Delete a HubDB Table
  hints:
    destructive: true
  name: deletehubdbtable
- description: HubSpot List HubDB Table Rows
  hints:
    readOnly: true
  name: listhubdbtablerows
- description: HubSpot Add a Row to a HubDB Table
  hints:
    readOnly: false
  name: addhubdbtablerow
- description: HubSpot Get a HubDB Table Row
  hints:
    readOnly: true
  name: gethubdbtablerow
- description: HubSpot Update a HubDB Table Row
  hints:
    readOnly: false
  name: updatehubdbtablerow
- description: HubSpot Delete a HubDB Table Row
  hints:
    destructive: true
  name: deletehubdbtablerow
- description: HubSpot Publish HubDB Table Draft
  hints:
    readOnly: false
  name: publishhubdbtabledraft
- description: HubSpot List All Domains
  hints:
    readOnly: true
  name: listdomains
- description: HubSpot Get a Domain by ID
  hints:
    readOnly: true
  name: getdomainbyid
- description: HubSpot Download a Source Code File
  hints:
    readOnly: true
  name: downloadsourcecodefile
- description: HubSpot Create a New Source Code File
  hints:
    readOnly: false
  name: createsourcecodefile
- description: HubSpot Create or Update a Source Code File
  hints:
    readOnly: false
  name: upsertsourcecodefile
- description: HubSpot Delete a Source Code File
  hints:
    destructive: true
  name: deletesourcecodefile
- description: HubSpot Retrieve File or Folder Metadata
  hints:
    readOnly: true
  name: getsourcecodemetadata
- description: HubSpot Validate a Source Code File
  hints:
    readOnly: false
  name: validatesourcecodefile
- description: HubSpot Extract a Zip Archive
  hints:
    readOnly: false
  name: extractzipfileasync
- description: HubSpot Get Extraction Task Status
  hints:
    readOnly: true
  name: getextractiontaskstatus
---
