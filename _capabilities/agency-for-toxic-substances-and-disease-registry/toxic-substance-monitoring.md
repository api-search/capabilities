---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Toxic Substance Monitoring
operations: []
personas:
- description: Researcher studying health effects of hazardous substance exposure in communities.
  id: public-health-researcher
  name: Public Health Researcher
- description: Government health officer assessing community exposure risks at contaminated sites.
  id: environmental-health-officer
  name: Environmental Health Officer
provider_name: Agency for Toxic Substances and Disease Registry
provider_slug: agency-for-toxic-substances-and-disease-registry
search_terms:
- research and monitoring workflow for hazardous substance toxicology data.
- exposure investigations and health consultations at contaminated sites.
- government health officer assessing community exposure risks at contaminated sites.
- researcher studying health effects of hazardous substance exposure in communities.
- health effects and exposure information for hazardous substances.
- hazardous materials
- minimum risk levels and safe exposure thresholds for chemicals.
- environmental health
- environmental health officer
- toxic substances
- public health
- diseases
- substance priority rankings based on toxicity and exposure frequency.
- federal government
- public health researcher
slug: toxic-substance-monitoring
source_filename: toxic-substance-monitoring.yaml
source_heading: Capability Spec
source_yaml: "name: Toxic Substance Monitoring\ndescription: \"Research and monitoring workflow for hazardous substance toxicology data from ATSDR including profiles, health guidance, and exposure investigations.\"\napisComposed:\n  - atsdr-toxic-substance-profiles-api\ntools:\n  - name: research-substance-toxicology\n    description: \"Look up toxicological profile for a specific hazardous substance to understand health effects and exposure routes.\"\n    sharedTool: atsdr-toxic-substance-profiles-api/list-toxicological-profiles\n  - name: get-minimum-risk-levels\n    description: \"Retrieve ATSDR Minimum Risk Levels for a substance to assess safe exposure thresholds by route and duration.\"\n    sharedTool: atsdr-toxic-substance-profiles-api/list-minimum-risk-levels\n  - name: check-priority-ranking\n    description: \"Check where a substance ranks on the ATSDR Substance Priority List based on toxicity and frequency at Superfund sites.\"\n    sharedTool: atsdr-toxic-substance-profiles-api/list-substance-priority-list\n\
  \  - name: find-exposure-investigations\n    description: \"Find ATSDR exposure investigations and health consultations near a location or involving specific contaminants.\"\n    sharedTool: atsdr-toxic-substance-profiles-api/list-exposure-investigations\npersonas:\n  - public-health-researcher\n  - environmental-health-officer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agency-for-toxic-substances-and-disease-registry/refs/heads/main/capabilities/toxic-substance-monitoring.yaml
tags: []
tools: []
---
