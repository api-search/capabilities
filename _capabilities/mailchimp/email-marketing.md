---
categories:
- customer-engagement
consumed_apis: []
description: Unified workflow combining Mailchimp Marketing API for campaigns, audiences, and analytics with the Transactional API for personalized email delivery. Used by marketing teams and developers to manage the full email lifecycle.
layout: capability
name: Mailchimp Email Marketing
operations:
- description: List campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get campaign details.
  method: GET
  name: get-campaign
  path: /v1/campaigns/{campaign_id}
- description: Delete a campaign.
  method: DELETE
  name: delete-campaign
  path: /v1/campaigns/{campaign_id}
- description: Send campaign.
  method: POST
  name: send-campaign
  path: /v1/campaigns/{campaign_id}/send
- description: List audiences.
  method: GET
  name: list-audiences
  path: /v1/audiences
- description: List members.
  method: GET
  name: list-members
  path: /v1/audiences/{list_id}/members
- description: Add a member.
  method: POST
  name: add-member
  path: /v1/audiences/{list_id}/members
- description: List reports.
  method: GET
  name: list-reports
  path: /v1/reports
- description: Get campaign report.
  method: GET
  name: get-report
  path: /v1/reports/{campaign_id}
- description: Send a transactional email.
  method: POST
  name: send-transactional
  path: /v1/transactional/send
- description: Search sent messages.
  method: POST
  name: search-transactional
  path: /v1/transactional/search
personas: []
provider_name: Mailchimp
provider_slug: mailchimp
search_terms:
- send transactional email.
- transactional search messages
- search transactional messages.
- marketing list campaigns
- transactional get user info
- marketing get report
- get campaign details.
- get details about a sent transactional message.
- send a marketing campaign.
- audience members.
- get report
- marketing list reports
- send a campaign.
- list all audiences.
- specific campaign.
- send a transactional email.
- marketing get campaign
- marketing get audience
- transactional get message info
- list audience members.
- add a member to an audience.
- list campaign reports.
- get a specific campaign report.
- list reports
- create a new marketing campaign.
- audience management.
- list audiences
- list members
- get transactional account information.
- delete campaign
- marketing list templates
- list email templates.
- transactional list templates
- list reports.
- send transactional
- send campaign.
- marketing list members
- search transactional
- get campaign
- list members.
- list campaigns
- create a campaign.
- list campaigns.
- add member
- campaign reports.
- marketing list automations
- add a member.
- get campaign report.
- transactional send message
- transactional send template
- search sent transactional messages.
- marketing delete campaign
- marketing campaigns.
- list transactional email templates.
- campaigns
- marketing list audiences
- list audiences.
- search sent messages.
- get audience details.
- send campaign
- list marketing automations.
- get a specific marketing campaign.
- create campaign
- list all marketing campaigns.
- send a transactional email with a template.
- newsletters
- marketing send campaign
- specific campaign report.
- marketing create campaign
- marketing automation
- transactional email
- delete a marketing campaign.
- marketing add member
- delete a campaign.
- email marketing
- mailchimp
slug: email-marketing
source_filename: email-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mailchimp Email Marketing\n  description: Unified workflow combining Mailchimp Marketing API for campaigns, audiences, and analytics with the Transactional\n    API for personalized email delivery. Used by marketing teams and developers to manage the full email lifecycle.\n  tags:\n  - Mailchimp\n  - Email Marketing\n  - Transactional Email\n  - Marketing Automation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MAILCHIMP_API_KEY: MAILCHIMP_API_KEY\n    MANDRILL_API_KEY: MANDRILL_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing\n    baseUri: https://server.api.mailchimp.com/3.0\n    description: Mailchimp Marketing API for email marketing and audience management.\n    authentication:\n      type: basic\n      username: anystring\n      password: '{{MAILCHIMP_API_KEY}}'\n    resources:\n    - name: campaigns\n      path: /campaigns\n      description: Email campaign\
  \ management.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List all campaigns.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new campaign.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            recipients:\n              list_id: '{{tools.list_id}}'\n            settings:\n              subject_line: '{{tools.subject_line}}'\n              from_name: '{{tools.from_name}}'\n              reply_to: '{{tools.reply_to}}'\n      - name: get-campaign\n        method: GET\n        description: Get a specific campaign.\n        inputParameters:\n        - name:\
  \ campaign_id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-campaign\n        method: PATCH\n        description: Update a campaign.\n        inputParameters:\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-campaign\n        method: DELETE\n        description: Delete a campaign.\n        inputParameters:\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: send-campaign\n        method: POST\n        description: Send a campaign.\n        inputParameters:\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: schedule-campaign\n        method: POST\n        description: Schedule a campaign.\n        inputParameters:\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            schedule_time: '{{tools.schedule_time}}'\n    - name: lists\n      path: /lists\n      description: Audience/list management.\n      operations:\n      -\
  \ name: list-audiences\n        method: GET\n        description: List all audiences.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-audience\n        method: POST\n        description: Create a new audience.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            permission_reminder: '{{tools.permission_reminder}}'\n      - name: get-audience\n        method: GET\n        description: Get a specific audience.\n        inputParameters:\n        - name: list_id\n          in: path\n          type: string\n          required: true\n          description: List/Audience ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: list-members\n        method: GET\n        description: List audience members.\n        inputParameters:\n        - name: list_id\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-member\n        method: POST\n        description: Add a member to an audience.\n        inputParameters:\n        - name: list_id\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email_address: '{{tools.email_address}}'\n            status: '{{tools.status}}'\n      - name: get-member\n        method: GET\n        description:\
  \ Get a specific member.\n        inputParameters:\n        - name: list_id\n          in: path\n          type: string\n          required: true\n          description: List ID\n        - name: subscriber_hash\n          in: path\n          type: string\n          required: true\n          description: Subscriber hash (MD5 of lowercase email)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automations\n      path: /automations\n      description: Marketing automations.\n      operations:\n      - name: list-automations\n        method: GET\n        description: List all automations.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-automation\n        method: GET\n        description: Get a specific automation.\n        inputParameters:\n        - name: workflow_id\n    \
  \      in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /templates\n      description: Email templates.\n      operations:\n      - name: list-templates\n        method: GET\n        description: List all templates.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-template\n        method: POST\n        description: Create a template.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            html: '{{tools.html}}'\n    - name: reports\n      path: /reports\n\
  \      description: Campaign reports and analytics.\n      operations:\n      - name: list-reports\n        method: GET\n        description: List campaign reports.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report\n        method: GET\n        description: Get a specific campaign report.\n        inputParameters:\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: transactional\n    baseUri: https://mandrillapp.com/api/1.0\n    description: Mailchimp Transactional API (Mandrill) for transactional email delivery.\n    authentication:\n      type: apikey\n      key: key\n      value: '{{MANDRILL_API_KEY}}'\n      placement:\
  \ body\n    resources:\n    - name: messages\n      path: /messages\n      description: Send and manage transactional messages.\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a new transactional email.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            message:\n              from_email: '{{tools.from_email}}'\n              to:\n              - email: '{{tools.to_email}}'\n              subject: '{{tools.subject}}'\n              html: '{{tools.html}}'\n      - name: send-template-message\n        method: POST\n        description: Send a transactional email using a template.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            template_name: '{{tools.template_name}}'\n            message:\n              to:\n              - email: '{{tools.to_email}}'\n      - name: search-messages\n        method: POST\n        description: Search recently sent messages.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            query: '{{tools.query}}'\n      - name: get-message-info\n        method: POST\n        description: Get information about a sent message.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n   \
  \         id: '{{tools.message_id}}'\n      - name: get-message-content\n        method: POST\n        description: Get the full content of a sent message.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            id: '{{tools.message_id}}'\n    - name: templates\n      path: /templates\n      description: Manage email templates.\n      operations:\n      - name: list-templates\n        method: POST\n        description: List all templates.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n      - name: get-template-info\n        method: POST\n        description: Get information about\
  \ a template.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            name: '{{tools.template_name}}'\n      - name: add-template\n        method: POST\n        description: Add a new template.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            name: '{{tools.name}}'\n            code: '{{tools.html}}'\n    - name: tags\n      path: /tags\n      description: Manage message tags.\n      operations:\n      - name: list-tags\n        method: POST\n        description: List all tags.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n      - name: get-tag-info\n        method: POST\n        description: Get information about a tag.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n            tag: '{{tools.tag}}'\n    - name: senders\n      path: /senders\n      description: Manage sending domains and addresses.\n      operations:\n      - name: list-senders\n        method: POST\n        description: List all senders.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n\
  \    - name: users\n      path: /users\n      description: Account information.\n      operations:\n      - name: get-user-info\n        method: POST\n        description: Get account information.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n    - name: webhooks\n      path: /webhooks\n      description: Webhook management.\n      operations:\n      - name: list-webhooks\n        method: POST\n        description: List all webhooks.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{MANDRILL_API_KEY}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: email-marketing-api\n    description: Unified\
  \ REST API for Mailchimp marketing campaigns and transactional email.\n    resources:\n    - path: /v1/campaigns\n      name: campaigns\n      description: Marketing campaigns.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List campaigns.\n        call: marketing.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a campaign.\n        call: marketing.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{campaign_id}\n      name: campaign-detail\n      description: Specific campaign.\n      operations:\n      - method: GET\n        name: get-campaign\n        description: Get campaign details.\n        call: marketing.get-campaign\n        with:\n          campaign_id: rest.campaign_id\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \     - method: DELETE\n        name: delete-campaign\n        description: Delete a campaign.\n        call: marketing.delete-campaign\n        with:\n          campaign_id: rest.campaign_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{campaign_id}/send\n      name: send-campaign\n      description: Send a campaign.\n      operations:\n      - method: POST\n        name: send-campaign\n        description: Send campaign.\n        call: marketing.send-campaign\n        with:\n          campaign_id: rest.campaign_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences\n      name: audiences\n      description: Audience management.\n      operations:\n      - method: GET\n        name: list-audiences\n        description: List audiences.\n        call: marketing.list-audiences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences/{list_id}/members\n\
  \      name: members\n      description: Audience members.\n      operations:\n      - method: GET\n        name: list-members\n        description: List members.\n        call: marketing.list-members\n        with:\n          list_id: rest.list_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-member\n        description: Add a member.\n        call: marketing.add-member\n        with:\n          list_id: rest.list_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Campaign reports.\n      operations:\n      - method: GET\n        name: list-reports\n        description: List reports.\n        call: marketing.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{campaign_id}\n      name: report-detail\n      description: Specific campaign report.\n      operations:\n  \
  \    - method: GET\n        name: get-report\n        description: Get campaign report.\n        call: marketing.get-report\n        with:\n          campaign_id: rest.campaign_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactional/send\n      name: transactional-send\n      description: Send transactional email.\n      operations:\n      - method: POST\n        name: send-transactional\n        description: Send a transactional email.\n        call: transactional.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactional/search\n      name: transactional-search\n      description: Search transactional messages.\n      operations:\n      - method: POST\n        name: search-transactional\n        description: Search sent messages.\n        call: transactional.search-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n\
  \    namespace: email-marketing-mcp\n    transport: http\n    description: MCP server for AI-assisted email marketing and transactional email.\n    tools:\n    - name: marketing-list-campaigns\n      description: List all marketing campaigns.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: marketing.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-get-campaign\n      description: Get a specific marketing campaign.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: marketing.get-campaign\n      with:\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-create-campaign\n      description: Create a new marketing campaign.\n      hints:\n        readOnly: false\n      call: marketing.create-campaign\n      with:\n        type: tools.type\n        list_id: tools.list_id\n        subject_line: tools.subject_line\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-send-campaign\n      description: Send a marketing campaign.\n      hints:\n        readOnly: false\n      call: marketing.send-campaign\n      with:\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-delete-campaign\n      description: Delete a marketing campaign.\n      hints:\n        readOnly: false\n        destructive: true\n      call: marketing.delete-campaign\n      with:\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-list-audiences\n      description: List all audiences.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: marketing.list-audiences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-get-audience\n      description: Get audience details.\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: marketing.get-audience\n      with:\n        list_id: tools.list_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-list-members\n      description: List audience members.\n      hints:\n        readOnly: true\n      call: marketing.list-members\n      with:\n        list_id: tools.list_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-add-member\n      description: Add a member to an audience.\n      hints:\n        readOnly: false\n      call: marketing.add-member\n      with:\n        list_id: tools.list_id\n        email_address: tools.email_address\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-list-automations\n      description: List marketing automations.\n      hints:\n        readOnly: true\n      call: marketing.list-automations\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: marketing-list-templates\n      description: List email templates.\n      hints:\n        readOnly: true\n      call: marketing.list-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-list-reports\n      description: List campaign reports.\n      hints:\n        readOnly: true\n      call: marketing.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketing-get-report\n      description: Get a specific campaign report.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: marketing.get-report\n      with:\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transactional-send-message\n      description: Send a transactional email.\n      hints:\n        readOnly: false\n      call: transactional.send-message\n      with:\n        from_email: tools.from_email\n\
  \        to_email: tools.to_email\n        subject: tools.subject\n        html: tools.html\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transactional-send-template\n      description: Send a transactional email with a template.\n      hints:\n        readOnly: false\n      call: transactional.send-template-message\n      with:\n        template_name: tools.template_name\n        to_email: tools.to_email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transactional-search-messages\n      description: Search sent transactional messages.\n      hints:\n        readOnly: true\n      call: transactional.search-messages\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transactional-get-message-info\n      description: Get details about a sent transactional message.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: transactional.get-message-info\n\
  \      with:\n        message_id: tools.message_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transactional-list-templates\n      description: List transactional email templates.\n      hints:\n        readOnly: true\n      call: transactional.list-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transactional-get-user-info\n      description: Get transactional account information.\n      hints:\n        readOnly: true\n      call: transactional.get-user-info\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mailchimp/refs/heads/main/capabilities/email-marketing.yaml
tags:
- Mailchimp
- Email Marketing
- Transactional Email
- Marketing Automation
tools:
- description: List all marketing campaigns.
  hints:
    openWorld: true
    readOnly: true
  name: marketing-list-campaigns
- description: Get a specific marketing campaign.
  hints:
    idempotent: true
    readOnly: true
  name: marketing-get-campaign
- description: Create a new marketing campaign.
  hints:
    readOnly: false
  name: marketing-create-campaign
- description: Send a marketing campaign.
  hints:
    readOnly: false
  name: marketing-send-campaign
- description: Delete a marketing campaign.
  hints:
    destructive: true
    readOnly: false
  name: marketing-delete-campaign
- description: List all audiences.
  hints:
    openWorld: true
    readOnly: true
  name: marketing-list-audiences
- description: Get audience details.
  hints:
    idempotent: true
    readOnly: true
  name: marketing-get-audience
- description: List audience members.
  hints:
    readOnly: true
  name: marketing-list-members
- description: Add a member to an audience.
  hints:
    readOnly: false
  name: marketing-add-member
- description: List marketing automations.
  hints:
    readOnly: true
  name: marketing-list-automations
- description: List email templates.
  hints:
    readOnly: true
  name: marketing-list-templates
- description: List campaign reports.
  hints:
    readOnly: true
  name: marketing-list-reports
- description: Get a specific campaign report.
  hints:
    idempotent: true
    readOnly: true
  name: marketing-get-report
- description: Send a transactional email.
  hints:
    readOnly: false
  name: transactional-send-message
- description: Send a transactional email with a template.
  hints:
    readOnly: false
  name: transactional-send-template
- description: Search sent transactional messages.
  hints:
    readOnly: true
  name: transactional-search-messages
- description: Get details about a sent transactional message.
  hints:
    idempotent: true
    readOnly: true
  name: transactional-get-message-info
- description: List transactional email templates.
  hints:
    readOnly: true
  name: transactional-list-templates
- description: Get transactional account information.
  hints:
    readOnly: true
  name: transactional-get-user-info
---
