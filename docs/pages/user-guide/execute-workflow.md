---
title: Quickstart-guide for executing a workflow
layout: default
nav_order: 2
parent: User Guide
---

# Quickstart Guide for Executing a Workflow

## pyiron
- ensure you have access to unix-like environment:
    - Linux & macOS will work right away
        1. install conda [link to conda](https://conda.io/projects/conda/en/latest/user-guide/install/index.html). We suggest to install the [miniforge distribution](https://github.com/conda-forge/miniforge), but any conda/mamba installation will work just fine.
        2. create a new environment based on `environment.yml` located in the unzipped folder: `conda env create -f environment.yml`. *Some workflows may not provide the section `name: <env_name>` line in `environment.yml`. In this case you may alter the command to `conda env create -f environment.yml -n <env_name>`*
        3. usually, pyiron and it's dependencies should be installed in the environment creation process. For more a detailed instruction on how to install pyiron, we refer to the [pyiron documentation](https://pyiron.readthedocs.io/en/latest/source/installation.html).
        4. start a jupyter session, e.g. `jupyter lab`
        5. open the notebook `<workflowname>.ipynb` and execute the workflow (i.e. run the notebook cells).
    - windows: use wsl or [anacondaprompt](https://conda.io/projects/conda/en/latest/user-guide/install/windows.html). *It's strongly suggested to use wsl, as it will ensure you can use all of the following instructions & suggestions right away.* With wsl, follow the linux instructions from above. If you choose to use anacondaprompt, you already have access to a conda installation and may start from step 2 onward.

### SimStack:
- [install](https://simstack.readthedocs.io/en/latest/installation/index.html)
- download and unpack
