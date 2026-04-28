---
categories: []
consumed_apis:
- iis-administration
description: Unified workflow for IT administrators to manage IIS web sites, applications, and application pools for enterprise web hosting on Windows Server.
layout: capability
name: Windows Server Web Management
operations:
- description: List all web sites
  method: GET
  name: list-websites
  path: /v1/websites
- description: Create a web site
  method: POST
  name: create-website
  path: /v1/websites
- description: Get web site details
  method: GET
  name: get-website
  path: /v1/websites/{id}
- description: Update a web site
  method: PATCH
  name: update-website
  path: /v1/websites/{id}
- description: Delete a web site
  method: DELETE
  name: delete-website
  path: /v1/websites/{id}
- description: List all applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Create an application
  method: POST
  name: create-application
  path: /v1/applications
- description: List all application pools
  method: GET
  name: list-application-pools
  path: /v1/application-pools
- description: Create an application pool
  method: POST
  name: create-application-pool
  path: /v1/application-pools
personas: []
provider_name: Microsoft Windows Server
provider_slug: microsoft-windows-server
search_terms:
- list all web applications
- server management
- list application pools
- delete website
- get web application details
- web server
- iis
- create website
- update a web site
- create a new iis web site
- list all applications
- get web site details
- update an application pool configuration
- get application
- windows server 2025
- single web site operations
- update application
- update website
- get application pool details
- create an application
- web application management
- delete a web site
- create application pool
- enterprise
- list all application pools
- update an iis web site configuration
- delete application pool
- list all iis application pools
- list all iis web sites on the server
- delete an iis web site
- create a web site
- delete a web application
- microsoft
- operating system
- list websites
- web site management
- list applications
- get details for a specific web site
- datacenter
- infrastructure
- create application
- delete application
- create an iis application pool
- update application pool
- delete an application pool
- create a new web application
- create an application pool
- get application pool
- get website
- application pool management
- list all web sites
- windows server
- update a web application
slug: web-server-management
tags:
- Microsoft
- Windows Server
- IIS
- Web Server
tools:
- description: List all IIS web sites on the server
  hints:
    openWorld: true
    readOnly: true
  name: list-websites
- description: Create a new IIS web site
  hints:
    readOnly: false
  name: create-website
- description: Get details for a specific web site
  hints:
    readOnly: true
  name: get-website
- description: Update an IIS web site configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-website
- description: Delete an IIS web site
  hints:
    destructive: true
  name: delete-website
- description: List all web applications
  hints:
    readOnly: true
  name: list-applications
- description: Create a new web application
  hints:
    readOnly: false
  name: create-application
- description: Get web application details
  hints:
    readOnly: true
  name: get-application
- description: Update a web application
  hints:
    idempotent: true
    readOnly: false
  name: update-application
- description: Delete a web application
  hints:
    destructive: true
  name: delete-application
- description: List all IIS application pools
  hints:
    readOnly: true
  name: list-application-pools
- description: Create an IIS application pool
  hints:
    readOnly: false
  name: create-application-pool
- description: Get application pool details
  hints:
    readOnly: true
  name: get-application-pool
- description: Update an application pool configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-application-pool
- description: Delete an application pool
  hints:
    destructive: true
  name: delete-application-pool
---
