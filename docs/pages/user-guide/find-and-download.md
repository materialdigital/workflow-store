---
title: Find and download workflows
layout: default
nav_order: 1
parent: User Guide
---


### Login
- log in using your material-digital account

### Find and download workflows
#### Using the website's UI
- browse the inventory or use the search feature
- select a workflow you are interested in.
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
