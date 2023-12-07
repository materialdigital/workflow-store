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
| workflow_environment | Mandatory | pyiron or SimStack |
| description | Mandatory | the description of the workflow |
| authors | Mandatory | a list of authors' names and optional their email addresses e.g. ["Author One <a1@example.de>", "Author Two <a2@example.de>"] |
| release | Mandatory | version information of the release |
| keywords | Mandatory | a list of keywords for the workflow (From a list of available keywords, making it possible to be queried via Ontology) |
| categories | Optional | a list of categories, e.g., atomistics, continuum, experimental|
| steps/codes | Optional | a list of steps/codes, e.g., LAMMPS, DAMASK, calculation of elastic modulus|
| licenses | Optional | a dictionary where the keys are the packages used in the workflow and the values are the corresponding license type. <br> e.g. 'pyiron':'BSD-3' |
| publications | Optional | a list of publications |
| logo | Optional | path to the logo of the workflow within the repository|