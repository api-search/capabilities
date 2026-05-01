---
categories:
- content-management
consumed_apis:
- blog-posts-api
- authors-api
- cms-pages-api
- cms-hubdb-api
- domains-api
- source-code-api
description: Content creation and management workflow for blog posts, authors, pages, domains, and source code.
layout: capability
name: HubSpot Content Management
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot delete a site page
- hubspot extract a zip archive
- hubspot create a landing page
- hubspot publish hubdb table draft
- updatehubdbtablerow
- cloneblogpost
- publishsitepage
- createblogpostlanguagevariation
- updateblogauthor
- hubspot validate a source code file
- hubspot read multiple blog posts
- marketing
- hubspot list all blog authors
- getblogpostrevisions
- detachblogauthorfromlanguagegroup
- hubspot get a hubdb table row
- batchupdateblogauthors
- listlandingpages
- hubspot archive a blog post
- email marketing
- createblogpost
- hubspot list site pages
- listblogposts
- createblogauthorlanguagevariation
- hubspot get a site page
- sales
- hubspot create multiple blog authors
- listdomains
- hubspot delete a source code file
- hubspot get revision history
- getextractiontaskstatus
- attachblogauthortolanguagegroup
- hubspot detach post from language group
- customer service
- getblogauthorbyid
- hubspot
- hubspot get a landing page
- addhubdbtablerow
- hubspot delete a landing page
- getlandingpage
- listhubdbtables
- validatesourcecodefile
- hubspot update a site page
- hubspot set new primary language
- hubspot create a blog author
- gethubdbtablerow
- listsitepages
- hubspot create a site page
- hubspot list hubdb table rows
- listhubdbtablerows
- analytics
- hubspot update a hubdb table row
- hubspot retrieve a blog author
- hubspot list landing pages
- archiveblogauthor
- hubspot attach author to language group
- deletehubdbtable
- batcharchiveblogauthors
- deletesourcecodefile
- hubspot update a hubdb table
- batchreadblogauthors
- hubspot update a blog author
- setblogpostlanguageprimary
- hubspot get a domain by id
- hubspot create a hubdb table
- commerce
- gethubdbtable
- pushblogpostdraftlive
- cms
- hubspot retrieve file or folder metadata
- getsourcecodemetadata
- marketing automation
- batchreadblogposts
- archiveblogpost
- hubspot archive multiple blog authors
- updatesitepage
- hubspot reset draft to live version
- updateblogpost
- hubspot retrieve a blog post
- deletehubdbtablerow
- batcharchiveblogposts
- hubspot attach post to language group
- hubspot clone a blog post
- hubspot update a blog post
- createsitepage
- operations
- scheduleblogpost
- hubspot list all domains
- extractzipfileasync
- deletesitepage
- crm
- hubspot create or update a source code file
- hubspot create a blog post
- setnewblogauthorlanguageprimary
- hubspot publish a site page
- detachblogpostfromlanguagegroup
- hubspot list hubdb tables
- hubspot read multiple blog authors
- hubspot get a hubdb table
- updatehubdbtable
- hubspot archive a blog author
- hubspot delete a hubdb table
- publishhubdbtabledraft
- getblogpostbyid
- getsitepage
- hubspot get extraction task status
- content
- hubspot push draft to live
- hubspot create multiple blog posts
- createblogauthor
- attachblogposttolanguagegroup
- hubspot restore a previous version
- hubspot list all blog posts
- hubspot archive multiple blog posts
- hubspot download a source code file
- createhubdbtable
- blogs
- hubspot delete a hubdb table row
- deletelandingpage
- restoreblogpostrevision
- batchcreateblogauthors
- hubspot create language variation
- batchcreateblogposts
- hubspot schedule a blog post
- hubspot update multiple blog authors
- hubspot add a row to a hubdb table
- listblogauthors
- getdomainbyid
- createlandingpage
- createsourcecodefile
- resetblogpostdraft
- downloadsourcecodefile
- hubspot detach author from language group
- batchupdateblogposts
- hubspot update multiple blog posts
- upsertsourcecodefile
- hubspot create a new source code file
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: HubSpot Content Management\n  description: Content creation and management workflow for blog posts, authors, pages, domains, and source code.\n  tags:\n  - HubSpot\n  - CMS\n  - Content\n  - Blogs\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - import: blog-posts-api\n    location: ./shared/blog-posts-api.yaml\n  - import: authors-api\n    location: ./shared/authors-api.yaml\n  - import: cms-pages-api\n    location: ./shared/cms-pages-api.yaml\n  - import: cms-hubdb-api\n    location: ./shared/cms-hubdb-api.yaml\n  - import: domains-api\n    location: ./shared/domains-api.yaml\n  - import: source-code-api\n    location: ./shared/source-code-api.yaml\n  exposes:\n  - type: mcp\n    port: 9091\n    namespace: content-management-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Content Management.\n\
  \    tools:\n    - name: listblogposts\n      description: HubSpot List All Blog Posts\n      hints:\n        readOnly: true\n      call: blog-posts-api.listblogposts\n    - name: createblogpost\n      description: HubSpot Create a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.createblogpost\n    - name: getblogpostbyid\n      description: HubSpot Retrieve a Blog Post\n      hints:\n        readOnly: true\n      call: blog-posts-api.getblogpostbyid\n    - name: updateblogpost\n      description: HubSpot Update a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.updateblogpost\n    - name: archiveblogpost\n      description: HubSpot Archive a Blog Post\n      hints:\n        destructive: true\n      call: blog-posts-api.archiveblogpost\n    - name: scheduleblogpost\n      description: HubSpot Schedule a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.scheduleblogpost\n    - name: cloneblogpost\n     \
  \ description: HubSpot Clone a Blog Post\n      hints:\n        readOnly: false\n      call: blog-posts-api.cloneblogpost\n    - name: pushblogpostdraftlive\n      description: HubSpot Push Draft to Live\n      hints:\n        readOnly: false\n      call: blog-posts-api.pushblogpostdraftlive\n    - name: resetblogpostdraft\n      description: HubSpot Reset Draft to Live Version\n      hints:\n        readOnly: false\n      call: blog-posts-api.resetblogpostdraft\n    - name: getblogpostrevisions\n      description: HubSpot Get Revision History\n      hints:\n        readOnly: true\n      call: blog-posts-api.getblogpostrevisions\n    - name: restoreblogpostrevision\n      description: HubSpot Restore a Previous Version\n      hints:\n        readOnly: false\n      call: blog-posts-api.restoreblogpostrevision\n    - name: batchreadblogposts\n      description: HubSpot Read Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batchreadblogposts\n    - name:\
  \ batchcreateblogposts\n      description: HubSpot Create Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batchcreateblogposts\n    - name: batchupdateblogposts\n      description: HubSpot Update Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batchupdateblogposts\n    - name: batcharchiveblogposts\n      description: HubSpot Archive Multiple Blog Posts\n      hints:\n        readOnly: false\n      call: blog-posts-api.batcharchiveblogposts\n    - name: detachblogpostfromlanguagegroup\n      description: HubSpot Detach Post from Language Group\n      hints:\n        readOnly: false\n      call: blog-posts-api.detachblogpostfromlanguagegroup\n    - name: setblogpostlanguageprimary\n      description: HubSpot Set New Primary Language\n      hints:\n        readOnly: false\n      call: blog-posts-api.setblogpostlanguageprimary\n    - name: attachblogposttolanguagegroup\n      description: HubSpot Attach Post to\
  \ Language Group\n      hints:\n        readOnly: false\n      call: blog-posts-api.attachblogposttolanguagegroup\n    - name: createblogpostlanguagevariation\n      description: HubSpot Create Language Variation\n      hints:\n        readOnly: false\n      call: blog-posts-api.createblogpostlanguagevariation\n    - name: listblogauthors\n      description: HubSpot List All Blog Authors\n      hints:\n        readOnly: true\n      call: authors-api.listblogauthors\n    - name: createblogauthor\n      description: HubSpot Create a Blog Author\n      hints:\n        readOnly: false\n      call: authors-api.createblogauthor\n    - name: getblogauthorbyid\n      description: HubSpot Retrieve a Blog Author\n      hints:\n        readOnly: true\n      call: authors-api.getblogauthorbyid\n    - name: updateblogauthor\n      description: HubSpot Update a Blog Author\n      hints:\n        readOnly: false\n      call: authors-api.updateblogauthor\n    - name: archiveblogauthor\n      description:\
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
