---
consumed_apis:
- mturk-requester
description: Workflow capability for data scientists and researchers to create HITs, manage worker assignments, approve work, and coordinate crowdsourced human intelligence tasks through Amazon Mechanical Turk.
layout: capability
name: Amazon Mechanical Turk - Crowdsourcing Workflow
operations:
- description: Create a new HIT for crowdsourced task execution.
  method: POST
  name: create-hit
  path: /v1/hits
- description: List all HITs in the requester account.
  method: GET
  name: list-hits
  path: /v1/hits
- description: List all assignments submitted for a HIT.
  method: GET
  name: list-assignments
  path: /v1/assignments
- description: Approve a completed assignment and release payment.
  method: POST
  name: approve-assignment
  path: /v1/assignments
- description: Send a bonus payment to a worker.
  method: POST
  name: send-bonus
  path: /v1/workers
- description: Get the current prepaid balance in the MTurk account.
  method: GET
  name: get-account-balance
  path: /v1/account
personas: []
provider_name: Amazon Mechanical Turk
provider_slug: amazon-mechanical-turk
search_terms:
- get the current prepaid balance available in the mturk requester account.
- get account balance
- list all active and reviewable hits in the requester account.
- list all worker assignments submitted for a specific hit for review.
- notify workers
- managing account balance and prepaid funds.
- reject assignment
- machine learning
- list qualification types used to filter and target the right worker pool.
- data scientist using mturk for data labeling, annotation, and validation tasks.
- review and manage worker assignment submissions.
- mechanical turk
- send a bonus payment to a worker for exceptional task completion.
- creating and managing hits for crowdsourced work.
- create hit
- list all assignments submitted for a hit.
- approve a completed worker assignment and release payment.
- reject a completed worker assignment with feedback.
- get the current prepaid balance in the mturk account.
- account balance and status.
- human intelligence
- manage worker bonuses and notifications.
- create a new human intelligence task for crowdsourced annotation, transcription, or research.
- crowdsourcing
- workflow for data scientists and researchers to manage hits and worker assignments on amazon mechanical turk.
- list assignments for hit
- academic or market researcher coordinating human intelligence tasks for studies and surveys.
- tasks
- create a new hit for crowdsourced task execution.
- send a bonus payment to a worker.
- labor
- list assignments
- get hit
- approve assignment
- get detailed information about a specific hit including status and completion metrics.
- send bonus
- amazon
- Data Scientist
- managing worker qualifications, blocks, bonuses, and notifications.
- aws
- send notification messages to specific workers.
- Researcher
- list all hits in the requester account.
- list qualification types
- approve a completed assignment and release payment.
- create and manage human intelligence tasks.
- list hits
slug: crowdsourcing-workflow
tags:
- Amazon
- Mechanical Turk
- Crowdsourcing
- Human Intelligence
- Tasks
- Machine Learning
tools:
- description: Create a new Human Intelligence Task for crowdsourced annotation, transcription, or research.
  hints:
    readOnly: false
  name: create-hit
- description: List all active and reviewable HITs in the requester account.
  hints:
    readOnly: true
  name: list-hits
- description: Get detailed information about a specific HIT including status and completion metrics.
  hints:
    readOnly: true
  name: get-hit
- description: List all worker assignments submitted for a specific HIT for review.
  hints:
    readOnly: true
  name: list-assignments-for-hit
- description: Approve a completed worker assignment and release payment.
  hints:
    readOnly: false
  name: approve-assignment
- description: Reject a completed worker assignment with feedback.
  hints:
    readOnly: false
  name: reject-assignment
- description: Send a bonus payment to a worker for exceptional task completion.
  hints:
    readOnly: false
  name: send-bonus
- description: Send notification messages to specific workers.
  hints:
    readOnly: false
  name: notify-workers
- description: Get the current prepaid balance available in the MTurk requester account.
  hints:
    readOnly: true
  name: get-account-balance
- description: List qualification types used to filter and target the right worker pool.
  hints:
    readOnly: true
  name: list-qualification-types
---
