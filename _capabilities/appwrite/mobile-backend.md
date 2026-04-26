---
consumed_apis:
- appwrite
description: Workflow capability for building mobile and web application backends using Appwrite. Provides AI-assisted management of users, databases, file storage, and backend configuration for developers building with Appwrite as their Backend-as-a-Service.
layout: capability
name: Appwrite Mobile Backend
operations: []
personas: []
provider_name: Appwrite
provider_slug: appwrite
search_terms:
- lists all registered users in the appwrite project backend
- creates a new user account in the appwrite backend for a mobile app
- administrator managing appwrite project users and configuration
- configure and manage a mobile app backend with appwrite
- applications
- list storage buckets
- backends
- provision user
- user authentication and account management
- lists file storage buckets configured in the appwrite backend
- appwrite
- developer building ios, android, or web apps with appwrite
- database and file storage management
- cloud function deployment and execution
- backend-as-a-service
- mobile
- lists appwrite databases available in the backend project
- list databases
- list project users
- developer tools
- open source
slug: mobile-backend
tags:
- Appwrite
- Mobile
- Backend-as-a-Service
- Open Source
- Developer Tools
tools:
- description: Lists all registered users in the Appwrite project backend
  hints:
    idempotent: true
    readOnly: true
  name: list-project-users
- description: Creates a new user account in the Appwrite backend for a mobile app
  hints:
    destructive: false
    readOnly: false
  name: provision-user
- description: Lists Appwrite databases available in the backend project
  hints:
    idempotent: true
    readOnly: true
  name: list-databases
- description: Lists file storage buckets configured in the Appwrite backend
  hints:
    idempotent: true
    readOnly: true
  name: list-storage-buckets
---
