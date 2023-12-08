---
title: User Guide
layout: default
permalink: /user-guide
nav_order: 2
---

## Documentation for workflowstore *users*

### Login
- log in on workflows.material-digital.de using your material-digital account

### Find and download workflows
#### Using the website's UI
- browse the inventory or use the search feature
- select a workflow you are interested in. *Note that each workflow requires one of the workflow environments supported by the PMD: pyiron or simstack*
- Click on download. You will recieve a zip-archive. Unpack it to your preferred destination.

#### Using the API
- make sure you are logged in
- click on 'User details' or navigate your browser to [https://workflows.material-digital.de/auth/user_details](https://workflows.material-digital.de/auth/user_details)
- click on 'Generate token' or directly navigate to [https://workflows.material-digital.de/get-token](https://workflows.material-digital.de/get-token) in your browser

##### Get all workflows
**Bash**
```bash
curl  -X GET \
  'https://workflows.material-digital.de/api/v1/resources/workflows' \
  --header 'Accept: */*' \
  --header 'Authorization: Bearer <your-api-key>'
```
**Python**
```python
import requests

reqUrl = "https://workflows.material-digital.de/api/v1/resources/workflows"
headersList = {
 "Accept": "*/*",
 "Authorization": "Bearer <your-api-token>" 
}
response = requests.request("GET", reqUrl, headers=headersList)
print(response.text)
```

Result:
```json
[
  {
    "id": 20,
    "name": "Test-WaNo",
    "url": "https://github.com/KIT-Workflows/Test-WaNo",
    "version": "version",
    "description": "This WaNo shows the most used functionalities available within the SimStack workflow framework."
  },
  ...
]
```

##### Download a single workflow
**Bash**
```bash
curl  -X GET \
  'https://workflows.material-digital.de/api/v1/resources/workflows/<workflow-id>' \
  --header 'Accept: */*' \
  --header 'Authorization: Bearer <your-api-key>'
  -O
```
**Python**
```python
import requests

reqUrl = "https://workflows.material-digital.de/api/v1/resources/<workflow-id>"
save_path = "target/path/file.zip"
headersList = {
 "Accept": "*/*",
 "Authorization": "Bearer <your-api-token>" 
}

r = requests.get(url, headers=headersList, stream=True)
with open(save_path, 'wb') as fd:
    for chunk in r.iter_content(chunk_size=chunk_size):
        fd.write(chunk)
```

### Quickstart-guide for executing a workflow
#### pyiron
- ensure you have access to unix-like environment:
    - Linux & macOS will work right away
    - windows: use wsl or [anacondaprompt](https://conda.io/projects/conda/en/latest/user-guide/install/windows.html). *It's strongly suggested to use wsl, as it will ensure you can use all of the following instructions & suggestions right away.*
        - install conda [link to conda](https://conda.io/projects/conda/en/latest/user-guide/install/index.html). We suggest to install the [miniforge distribution](https://github.com/conda-forge/miniforge), but any conda/mamba installation will work just fine.
        - create a new environment based on `environment.yml` located in the unzipped folder: `conda env create -f environment.yml`. *Some workflows may not provide the section `name: <env_name>` line in `environment.yml`. In this case you may alter the command to `conda env create -f environment.yml -n <env_name>`*
        - usually, pyiron and it's dependencies should be installed in the environment creation process. For more a detailed instruction on how to install pyiron, we refer to the [pyiron documentation](https://pyiron.readthedocs.io/en/latest/source/installation.html).
        - start a jupyter session, e.g. `jupyter lab`
        - open the notebook `<workflowname>.ipynb` and execute the workflow (i.e. run the notebook cells).

#### simstack:
- [install](https://simstack.readthedocs.io/en/latest/installation/index.html)
- download and unpack
