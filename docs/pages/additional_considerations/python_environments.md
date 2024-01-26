---
title: Python Environments
layout: default
nav_order: 5
parent: Additional Considerations
grand_parent: Contributor QuickStart Guide
---

## Exporting a Python Environment
{: .no_toc}

To ensure consistency and reproducibility, it's a good practice to export your Python environment into a requirements file. This file captures all the dependencies and their versions, making it easy for others to recreate the same environment.

### Table of Contents
{: .no_toc .text-delta}

1. TOC
{:toc}

### For pip/PyPI

#### 1. Activate Your Virtual Environment (if applicable):

If you're working within a virtual environment (e.g. mamba or venv), activate it using the following command:
```bash
source venv/bin/activate  # Linux/macOS
```
```bash
venv\Scripts\activate  # Windows
```

#### 2. Install pip-tools (if not installed):

To simplify the process of managing requirements files, install pip-tools using:

```bash
pip install pip-tools
```

#### 3. Generate requirements.txt:

Use `pip freeze` to generate a requirements.txt file containing all your project dependencies:

```bash
pip freeze > requirements.txt
```

#### 4. Review requirements.txt:

Open the generated requirements.txt file in a text editor. It should look similar to this:

```plaintext
package1==1.0.0
package2>=2.1.0,<3.0.0
...
```

Ensure that all the necessary packages and their versions are listed.

#### 5. Share requirements.txt:

Include the requirements.txt file in your project repository. Others can then recreate your Python environment using the following command:

```
pip install -r requirements.txt
```

This installs all the dependencies specified in the file.
 Additional Considerations:

#### Pin Specific Versions:
    
It's recommended to pin specific versions of your dependencies. This ensures that others will use the exact same versions that you used during development.

#### Update requirements.txt regularly:
    
As you add or remove dependencies, remember to update your requirements.txt file. This keeps it synchronized with your actual environment.

#### Include Development Dependencies (Optional):
    
If your project has dependencies for development (e.g., testing libraries), include them in a separate file, such as requirements-dev.txt.

### For conda

To ensure reproducibility, it's recommended to export and share your Conda environment, especially if you are using Conda to manage your project dependencies. Follow these steps to export and share your Conda environment:

#### 1. Activate your conda environment (if applicable):

If you're working within a Conda environment, activate it using the following command:

```bash
conda activate myenv
```

#### 2. Export environment to YAML file:

Use the following command to export your Conda environment to a YAML file (e.g., `environment.yml`):

```bash
conda env export --from-history > environment.yml
```

#### 3. Review `environment.yml`:

Open the generated `environment.yml` file in a text editor. It should look similar to this:

```yaml
name: myenv
channels:
  - defaults
dependencies:
  - python=3.8
  - other_dependency=1.2.3
  # Add other dependencies here
```

Ensure that all the necessary packages and their versions are listed.

### Sharing conda environments

#### 1. Include `environment.yml` in your repository:

Commit the `environment.yml` file to your project repository. This file will be used by others to recreate your conda environment.

#### 2. To reproduce the conda environment:

Others can recreate your conda environment using the following command:

```bash
conda env create -f environment.yml
```

This command reads the `environment.yml` file and creates a new conda environment named `myenv`.

#### 3. Activate the new environment:

Activate the new conda environment:

```bash
conda activate myenv
```

Now, the user's Python environment should match yours, ensuring consistency across different machines.

### Additional Considerations:

- **Update `environment.yml` Regularly:**
  As you add or remove dependencies, remember to update your `environment.yml` file. This keeps it synchronized with your actual environment.

- **Include Conda Environment in Documentation:**
  Mention in your documentation that users should refer to the `environment.yml` file for setting up the Conda environment.
