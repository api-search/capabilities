---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Airbnb Listing Management
operations: []
personas: []
provider_name: airbnb
provider_slug: airbnb
search_terms: []
slug: airbnb-listing-management
source_filename: airbnb-listing-management.yaml
source_heading: Capability Spec
source_yaml: "name: Airbnb Listing and Reservation Management\ndescription: Workflow capability for managing Airbnb listings, reservations, and experiences\nversion: 1.0.0\ntype: workflow\nmcp_tools:\n- name: manage_listing\n  description: Create, update, or retrieve an Airbnb property listing\n  inputs:\n    action: string\n    listing_id: string\n    listing_data: object\n  outputs:\n    listing: object\n    success: boolean\n  rest_adapter:\n    ref: airbnb-api\n    operations:\n    - createListing\n    - updateListing\n    - getListing\n- name: manage_calendar\n  description: Get or update listing availability and pricing on the calendar\n  inputs:\n    listing_id: string\n    start_date: string\n    end_date: string\n    updates: array\n  outputs:\n    calendar_days: array\n    success: boolean\n  rest_adapter:\n    ref: airbnb-api\n    operations:\n    - getCalendar\n    - updateCalendar\n- name: get_reservations\n  description: Retrieve a list of reservations, optionally filtered\
  \ by status or date\n  inputs:\n    listing_id: string\n    status: string\n    start_date: string\n    end_date: string\n  outputs:\n    reservations: array\n    total: integer\n  rest_adapter:\n    ref: airbnb-api\n    operations:\n    - listReservations\n- name: send_message\n  description: Send a message to a guest within a reservation thread\n  inputs:\n    reservation_id: string\n    message: string\n  outputs:\n    message_id: string\n    success: boolean\n  rest_adapter:\n    ref: airbnb-api\n    operations:\n    - createMessage\n- name: manage_experience\n  description: Create or update an Airbnb Experience listing\n  inputs:\n    action: string\n    experience_id: string\n    experience_data: object\n  outputs:\n    experience: object\n    success: boolean\n  rest_adapter:\n    ref: airbnb-api\n    operations:\n    - createExperience\n    - updateExperience\n    - getExperience\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/airbnb/refs/heads/main/capabilities/airbnb-listing-management.yaml
tags: []
tools: []
---
