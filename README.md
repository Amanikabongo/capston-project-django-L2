# RockstarSite

Welcome to the RockstarSite Django project. this project is considered as a fictional band of musicians it include functions such as ticket sales, login page, registration, band members events and so on . This guide provides step-by-step instructions to access and run the project locally. It includes adding necessary files, initializing Git, creating branches, documenting code, generating user-friendly documentation, containerizing the app, and pushing it to a remote repository.

## Link to my repository: https://github.com/Amanikabongo/capston-project-django-L2
## Link to my Docker hub repository : https://hub.docker.com/r/amani101/rockstarsite
## Run this code on docker Playground
# Create a new instance run the following Pull command:
```sh
docker pull amani101/rockstarsite
```
# Next use this Run commmand to view the image
```sh
docker run -it amani101/rockstarsite:latest
```


## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup and Installation](#setup-and-installation)
  - [Clone the Repository](#clone-the-repository)
  - [Create and Activate a Virtual Environment](#create-and-activate-a-virtual-environment)
  - [Install Dependencies](#install-dependencies)
- [Initialize Git](#initialize-git)
  - [Add a .gitignore File](#add-a-gitignore-file)
  - [Create a Requirements File](#create-a-requirements-file)
- [Branching and Documentation](#branching-and-documentation)
  - [Create and Switch to the Docs Branch](#create-and-switch-to-the-docs-branch)
  - [Add Docstrings and Commit](#add-docstrings-and-commit)
  - [Generate Documentation with Sphinx](#generate-documentation-with-sphinx)
- [Containerizing the App](#containerizing-the-app)
  - [Create and Switch to the Container Branch](#create-and-switch-to-the-container-branch)
  - [Create and Add a Dockerfile](#create-and-add-a-dockerfile)
- [Merging and Finalizing](#merging-and-finalizing)
  - [Merge Branches](#merge-branches)
  - [Add and Commit a README.md File](#add-and-commit-a-readme-md-file)
  - [Push to Remote Repository](#push-to-remote-repository)
  - [Submit Link in capstone.txt](#submit-link-in-capstonetxt)

## Prerequisites

Ensure you have the following installed:
- Python (3.6 or higher)
- pip
- Git
- Docker

## Setup and Installation

### Clone the Repository

Clone the repository to your local machine:

```sh
git clone https://github.com/your-username/rockstarsite.git
cd rockstarsite
```
## Create and Activate a Virtual Environment

Create and activate a virtual environment:

```sh
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```
## Install Dependencies
Install the necessary dependencies from requirements.txt:
```sh
pip install -r requirements.txt
```

## Initialize Git
```sh
git int
```
### Add a .gitignore File
## Create a .gitignore file in the root directory to exclude generated files:
```sh
*.pyc
__pycache__/
db.sqlite3
/media
/static
.env
.venv/
.vscode/
.idea/
.DS_Store
```
## Create a Requirements File
Generate a requirements.txt file if it doesn't exist:
```sh
pip freeze > requirements.txt
```
# Branching and Documentation
## Create and Switch to the Docs Branch
Create and switch to a new branch for documentation:
```sh
git checkout -b docs
```
## Add Docstrings and Commit
```sh
git add views.py  # Replace with actual file names
git commit -m "Add docstrings to views.py"

git add models.py  # Replace with actual file names
git commit -m "Add docstrings to models.py"
```
## Generate Documentation with Sphinx
Set up Sphinx and generate user-friendly documentation:
#Install Sphinx:
```sh
pip install sphinx
```
## Initialize Sphinx:
```sh
sphinx-quickstart docs
```
## Configure conf.py:
Add the following to conf.py:
```sh
import os
import sys
import django

sys.path.insert(0, os.path.abspath('..'))
os.environ['DJANGO_SETTINGS_MODULE'] = 'rockstarsite.settings'
django.setup()
```
## Build documentation
```sh
sphinx-build -b html . _build/html
```
## Containerizing the App
Create and switch to a new branch for containerization:
```sh
git checkout -b container
```
## Create and Add a Dockerfile
Create a Dockerfile with the following content or create your own depending on what system you currently using:
```sh
# Use an official Python runtime as a base image
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the current directory contents into the container
COPY . /app

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Run the Django app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```
## Add and commit the Dockerfile:
```sh
git add Dockerfile
git commit -m "Add Dockerfile"
```
## Merging and Finalizing
## Merge Branches
Switch to the main branch and merge the docs and container branches:
```sh
git checkout main
git merge docs
git merge container
```











