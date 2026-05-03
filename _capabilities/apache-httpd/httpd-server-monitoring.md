---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Httpd Server Monitoring
operations: []
personas: []
provider_name: Apache HTTP Server
provider_slug: apache-httpd
search_terms:
- reverse proxy
- load balancer
- proxy
- open source
- apache
- web server
slug: httpd-server-monitoring
source_filename: httpd-server-monitoring.yaml
source_heading: Capability Spec
source_yaml: "name: Apache HTTP Server Monitoring\ndescription: Workflow capability for monitoring Apache HTTP Server status, worker performance, and load balancer state\npersona: Platform Engineer\nworkflow:\n  - step: server-status\n    name: Get Server Status\n    description: Retrieve request rates, worker states, and system load from mod_status\n    capability: httpd-status\n    operation: getServerStatus\n    server:\n      rest: http://localhost:80\n      mcp: http://localhost:9090\n\n  - step: server-info\n    name: Get Server Info\n    description: Retrieve loaded modules and configuration from mod_info\n    capability: httpd-status\n    operation: getServerInfo\n    server:\n      rest: http://localhost:80\n      mcp: http://localhost:9090\n\n  - step: balancer-status\n    name: Get Balancer Status\n    description: Check load balancer pool health and member assignments\n    capability: httpd-status\n    operation: getBalancerManager\n    server:\n      rest: http://localhost:80\n\
  \      mcp: http://localhost:9090\n\ntools:\n  - name: getServerStatus\n    description: Get Apache httpd server status metrics\n    server:\n      rest:\n        baseUrl: http://localhost:80\n        path: /server-status\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getServerStatus\n        method: POST\n\n  - name: getServerInfo\n    description: Get Apache httpd server module and configuration info\n    server:\n      rest:\n        baseUrl: http://localhost:80\n        path: /server-info\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getServerInfo\n        method: POST\n\n  - name: getBalancerManager\n    description: Get load balancer pool and member status\n    server:\n      rest:\n        baseUrl: http://localhost:80\n        path: /balancer-manager\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getBalancerManager\n        method: POST\n\
  \n  - name: updateBalancerMember\n    description: Update load balancer member status or weight\n    server:\n      rest:\n        baseUrl: http://localhost:80\n        path: /balancer-manager\n        method: POST\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/updateBalancerMember\n        method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-httpd/refs/heads/main/capabilities/httpd-server-monitoring.yaml
tags: []
tools: []
---
