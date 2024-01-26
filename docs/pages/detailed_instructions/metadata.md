---
title: Metadata
layout: default
nav_order: 1
parent: Detailed Instructions
grand_parent: Contributor QuickStart Guide
---

### Metadata

In order to register the workflow in the PMD workflow store, the file `meta.json` is required. The file includes the essential metadata. The keys and their possible values are listed in the following table:

| Key | Requirement | Description|
|-----|------------|------------|
| title | Mandatory | the Label of the workflow |
| workflow_environment | Mandatory | e.g. "pyiron" or "SimStack" |
| description | Mandatory | the description of the workflow |
| keywords | Mandatory | a list of (self-chosen) keywords for the workflow |
| categories | Optional | a list of (self-chosen) categories, e.g., atomistics, continuum, experimental |
| logo | Optional | path to the logo of the workflow within the repository |

A fully specified `meta.json` has the following format:

```json
{
    "title": "Exciting science experiment",
    "workflow_environment": "pyiron",
    "description": "Code to run new physics",
    "keywords": [
        "workflow",
        "simulation"
    ],
    "categories":[
        "atomistics"
    ],
    "logo": "path/to/logo.jpg"
}
```
