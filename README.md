[![CircleCI](https://dl.circleci.com/status-badge/img/gh/nguyennhutamthien1993/DevOps_Microservices/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/nguyennhutamthien1993/DevOps_Microservices/tree/main)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Structure
1. The `.circleci` folder includes a `config.yml` file that check project code build status. It is indicated by a badge status is attached at Top of README.md
2. The `output_txt_files` folder contains the log output from a prediction which is made
3. The `app.py` file contains code of Flask app Make a prediction home
4. The `Dockerfile` file contains steps to structure Docker image for app prediction a home
5. The `make_prediction.sh` file contains query Docker hub or Kubernetes cluster with response of a prediction data
6. The `Makefile` file contains steps to build virtual environment, install dependences, build software and lint app code
7. The `requirements.txt` file contains dependences we need for our application
8. The `run_docker.sh` file contains steps to build a docker image of our application
9. The `run_kubernetes.sh` file contains step to run Docker Hub with kubernetes and forward container port in Kubernetes Cluster
10. The `upload_docker.sh` file contains step to publish our docker image to Docker Hub