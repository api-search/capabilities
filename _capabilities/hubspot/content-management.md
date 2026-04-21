---
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
- updatehubdbtablerow
- hubspot read multiple blog authors
- downloadsourcecodefile
- hubspot set new primary language
- gethubdbtable
- batchreadblogauthors
- analytics
- content
- attachblogauthortolanguagegroup
- listhubdbtablerows
- hubspot publish hubdb table draft
- hubspot create a new source code file
- hubspot retrieve file or folder metadata
- batchupdateblogposts
- deletehubdbtablerow
- publishhubdbtabledraft
- commerce
- hubspot create or update a source code file
- hubspot create a blog author
- hubspot update a site page
- hubspot restore a previous version
- setblogpostlanguageprimary
- hubspot delete a source code file
- hubspot update a blog author
- hubspot validate a source code file
- cms
- publishsitepage
- extractzipfileasync
- sales
- email marketing
- attachblogposttolanguagegroup
- hubspot archive a blog post
- hubspot list landing pages
- marketing
- blogs
- hubspot get a hubdb table
- deletehubdbtable
- hubspot delete a site page
- hubspot create a landing page
- getsitepage
- listblogposts
- scheduleblogpost
- hubspot create a blog post
- hubspot list all domains
- hubspot create multiple blog posts
- hubspot retrieve a blog post
- hubspot
- batchreadblogposts
- createblogpostlanguagevariation
- hubspot download a source code file
- validatesourcecodefile
- upsertsourcecodefile
- hubspot get a site page
- listsitepages
- getlandingpage
- batcharchiveblogauthors
- hubspot attach post to language group
- pushblogpostdraftlive
- listdomains
- listlandingpages
- hubspot update multiple blog posts
- getblogauthorbyid
- hubspot create a hubdb table
- hubspot push draft to live
- deletelandingpage
- hubspot archive multiple blog authors
- setnewblogauthorlanguageprimary
- hubspot detach author from language group
- hubspot list all blog authors
- createsitepage
- updatesitepage
- hubspot get a domain by id
- getblogpostbyid
- hubspot create a site page
- archiveblogauthor
- hubspot update a blog post
- hubspot attach author to language group
- createblogauthor
- updatehubdbtable
- deletesitepage
- hubspot detach post from language group
- batchupdateblogauthors
- detachblogpostfromlanguagegroup
- hubspot list hubdb table rows
- hubspot create multiple blog authors
- gethubdbtablerow
- hubspot delete a hubdb table row
- operations
- updateblogauthor
- listhubdbtables
- updateblogpost
- hubspot list site pages
- getdomainbyid
- hubspot list hubdb tables
- hubspot archive a blog author
- createhubdbtable
- hubspot get extraction task status
- hubspot extract a zip archive
- hubspot get revision history
- hubspot update a hubdb table row
- hubspot retrieve a blog author
- hubspot create language variation
- createsourcecodefile
- customer service
- cloneblogpost
- archiveblogpost
- batcharchiveblogposts
- hubspot archive multiple blog posts
- detachblogauthorfromlanguagegroup
- hubspot publish a site page
- addhubdbtablerow
- hubspot list all blog posts
- getsourcecodemetadata
- hubspot update multiple blog authors
- hubspot get a landing page
- hubspot update a hubdb table
- getblogpostrevisions
- listblogauthors
- createblogpost
- createblogauthorlanguagevariation
- createlandingpage
- hubspot reset draft to live version
- deletesourcecodefile
- restoreblogpostrevision
- hubspot delete a hubdb table
- resetblogpostdraft
- hubspot clone a blog post
- crm
- getextractiontaskstatus
- hubspot get a hubdb table row
- batchcreateblogauthors
- hubspot schedule a blog post
- hubspot delete a landing page
- marketing automation
- hubspot add a row to a hubdb table
- batchcreateblogposts
- hubspot read multiple blog posts
slug: content-management
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
