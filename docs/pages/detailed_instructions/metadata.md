---
title: Metadata
layout: default
nav_order: 1
parent: Detailed Instructions
---

### Metadata
In order to register the workflow in the PMD workflow store, the file `meta.json` is required. The file includes the essential metadata. The keys and their possible values are listed in the following table:

| Key | Requirement | Description|
|-----|------------|------------|
| title | Mandatory | the Label of the workflow |
| workflow_environment | Mandatory | "pyiron" or "SimStack" |
| description | Mandatory | the description of the workflow |
| keywords | Mandatory | a list of (self-chosen) keywords for the workflow |
| categories | Optional | a list of (self-chosen) categories, e.g., atomistics, continuum, experimental |
| logo | Optional | path to the logo of the workflow within the repository |
