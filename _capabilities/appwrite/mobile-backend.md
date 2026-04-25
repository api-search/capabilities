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
- backend-as-a-service
- administrator managing appwrite project users and configuration
- creates a new user account in the appwrite backend for a mobile app
- mobile
- appwrite
- configure and manage a mobile app backend with appwrite
- user authentication and account management
- cloud function deployment and execution
- lists appwrite databases available in the backend project
- open source
- provision user
- lists file storage buckets configured in the appwrite backend
- applications
- developer tools
- list databases
- database and file storage management
- list project users
- lists all registered users in the appwrite project backend
- developer building ios, android, or web apps with appwrite
- list storage buckets
- backends
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
