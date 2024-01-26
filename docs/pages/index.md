---
title: Contributor QuickStart Guide
layout: page
permalink: /
nav_order: 1
has_children: true
---

# How do I upload to the Workflow Store?


## Introduction

The Workflow Store provides a place to share your science with others! Upload and share the code that can be used to reproduce some or all of your research. **They can be works in progress!**

## Quick start Guide

> **Note:** Most of the instructions below link to  formats, concepts, or standards for GitHub, which should work in a similar/identical form for GitLab.

### 1. Put your code in version control

Make sure your code is under version control and stored in a registry such as GitHub or a GitLab instance.

Create a new repository (e.g. on [GitHub](https://github.com/new)). Ensure `initialize the repository with a Readme` is deselected and follow the instructions applicable to your situation. For example, you may want to upload an existing directory.
### 2. Add meta information

Add a `meta.json` for the [PMD Workflow Store](https://workflows.material-digital.de/). You can also use a [web form](https://json-editor.github.io/json-editor/?data=N4Ig9gDgLglmB2BnEAuUBXRBTA+vAhgLa75RQBOMARulFsihelgDQgTliHQ5VYBmYcrgAmWADZY6qJqxCZRA/OnFQcAN3zjmDWW0L4AHjjHQAFqgAMbGmQQ5EUUrkJgxqAIxsAxvmwOsJBhYdVwOSCxyKABPAPxybwtGcmY2GG8EcWpUEEF4JwB3ei4sAFYQNjAqACssbzVxfGiwWhz4IQNxCpBERKwDVFAAEl6zfvwcszIIFAB6WerEBABaUfGAOiEAc1mRcnx+KGXLABZZtYMAYm7YKEkcgAUAWQARAAIAdSEAa35xMAKbyeUnwIlIEzYMQgWByVVq9W6wgAjugYMIRKgANogW73NgFH5/AE4QLqNEIYj5bpiXqUaBweDdZRQMxCZBsYSSPwwtjfLDRAnkETIAC6bFBImCDK0D040KiMHoqH4WmwbHC8tgSrQOOC9x1UJhKB6FBg8C21Po3jpsAQOQAKmM3o0+OI3mB+G8WVg3oLfv8CutLSqVFAck9or7CQGQABffHR4mk8nwSlhg3RaE5RyUc3dQLoQhY9jRFPdADKMEI5ac3m+3TA3vIIDFIBp1pg9LtxsdPr9RMByc4qcCUBYbywwTG5DeAHIIKXh7P3TPZ5Xq7XvrOg/G21abQzBjjM0aTbmLWx2wfuyBe28r53bfB3Z7vVHyP6ATvxbRWeQGKAho5PE+zRN0wT9ABx5ZsaOZmhau6EGaACSdCEAwXh7rSj6HsaACCzowI4L5vMyf6IMuBDEIgpHwCI7pdgQbremiE4GDAboSsIiDYIg45YOsWzrOOmKznhv5CG8ADy8A+vgHgAAJYIYRAQJI6xiLO45iRJM72gSpEAExKSp3DqZpIrfiAnJYNyR5AbBpp5pe+44TeABqkSIAybxmoI5AGE+JFvjZ3JWXyApCMK9knsB5CgeBaFQQ5Z7wXG+goUlngudhjE5ARWTER6bwRYKwpvP5XpOv2AbjgY3zwb5UBvBAYA8dQkhemAbx8G8KKRIq9Fkvg0n5GA/xbNEVm+HQWxCIqyWxcaIFNIlkExTBqXOSABZFig2KkFwRGwN47IgBk+Rmughb5oY8pVqOWgNk2LaIZl60oNYWEdnl+GEUVnozVgc2UPQ/GCcJpFQEdjjpHxbwXbA8DXYQ/F3QNaZaFZjhYBAiCzBkNIbaeK1gWkWUZptcF5m98CoR9mEPr9IAFcdJE43jBNuGDE4Q+OAAyeFPE8DzluOLxC3h5YANLjr44jeCopA+cVEh+CdbyuCIKiYFZWTeIEvHE7CNR1GGGXwLKEQKtqX0SlKCAynKkRaotVNOQhOU/U++X3ukT7xJGBTTj6b4RTR8Sh06ED4HW+BbPQbwKPRZpVX2iYFOO+B0WnbyaNoieR7nGTxfQrV0Y1+uG6HJ7rG8ACifNvMA86Lggs4oLOABC5YvMsADMs6xkGLkhqoR4LmWxo933/dxruEDoFQ+vKwgbsk/Fq3kx9gFLVtnsgEhdMU19TM+8aUmMVo/3NcVi/L+kq9IG8nLOPR0O5zVX7pSAE1gMbjlzyWlyufEAl8A5uhjiyLquc/7BWqhnX0U5U4hVxm1YIQgprz13IgVkBQSTxTZDkM0dB9j1EPJCMYxAchUDAI2HM+AIAnHnkAA) to do so.

Sample `meta.json`:

```json
{
    "workflow_environment":"pyiron",
    "title": "Exciting science experiment",
    "authors": [
        "John Doe <john.doe@science.com>",
        "John Smith <john.smith@institute.edu>"
    ],
    "description": "Code to run new physics",
    "release": "0.0.1",
    "keywords": [
        "workflow",
        "simulation"
    ],
    "categories":[
        "atomistics"
    ]
}
```

Full info on the file format [here](pages/detailed_instructions/metadata).

### 3. Add a README (optional)

Add a Readme with instructions and tips on setup and useage of your workflow.

[Further suggestions on creating your Readme](pages/additional_considerations/readme)

### 4. Add a License (optional)

If you care about proper software sharing, [choose a license](https://choosealicense.com/) and add a `LICENSE` file. 

### 5. Add citation info (optional)
#### Minimal format
Citations can be added as a short section in  your Readme:

> If you are using this workflow please cite:
Author Name *et al.* (2023) *"Title of publication."* Journal [Vol], p1-10 DOI:..." 

#### Citation File (optional)
The prefered method to add citations is to include
a [`CREDENTIALS.cff` file](https://citation-file-format.github.io/) in your repository.

### 6. Create a release/tag
Commit all required files and create a release with an associated [release tag](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository#creating-a-release)

### 7. Upload to the Workflow Store

1. Login to the [workflow Store](https://workflows.material-digital.de/) (via the button in the top right)
2. [Upload your workflow](https://workflows.material-digital.de/upload_workflow/)

Detailed instructions including information on how to add private repositories are provided in the [upload workflow section](pages/detailed_instructions/upload/).
