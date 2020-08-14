[![CircleCI](https://circleci.com/gh/circleci/circleci-docs.svg?style=svg)](https://circleci.com/gh/circleci/circleci-docs)

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

---

## Setup the Environment

* Create a virtualenv and activate it
  `python3 -m venv ~/.devops` <br />
  `source ~/.devops/bin/activate`
  
* Run `make install` to install the necessary dependencies
* For Ubuntu users, you must install `hadolint`to the project directory and make sure that its added to the /usr/bin/ 
To test hadolint alone, run: `hadolint Dockerfile` <br />
If it did not give any output, this means its working fine. 
Dockerfile is the file that has the steps to set up your image and create a container later from it.

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Upload Dockerfile to DockerHub
1. Create an account on DockerHub and have a unique ID 
2. `./run_docker.sh`
3. `./upload_docker.sh`
This operation may take a while to finish.

### Kubernetes Steps
Our goal:
* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl 
<br />
 Minikub MUST be running locally and started before being able to use `kubectl` and execute its commands. <br />
Steps:
1- Download and install minikube locally accroding to your operating system
2- To start minikube run `minikube start`
3- Install `kubectl` locally
4- Make sure it's installed correctly by running `minikube version`
4- Check it works by running a command `kubectl version`
Now we're able to make predictions. <br />
1- Run `./run_docker.sh` <br/>
2- Run `./make_prediction.sh`
