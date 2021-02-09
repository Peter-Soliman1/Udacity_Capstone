[![ASa3ed](https://circleci.com/gh/ASa3ed/Udacity_Capstone.svg?style=svg)](https://circleci.com/gh/ASa3ed/Udacity_Capstone)

                    Udacity AWS Cloud DevOps Engineer Nanodegree Program 
                                    Capstone Project 

## Project Overview

It's a small pipeline implementation for a html web app using :
* Working in AWS
* Using Jenkins or Circle CI to implement Continuous Integration and Continuous Deployment
* Building pipelines
* Working with Ansible and CloudFormation to deploy clusters
* Building Kubernetes clusters
* Building Docker containers in pipelines


### Project Tasks

* Linting html app and Dockerfile 

* Pushing the built Docker container(s) to the Docker repository (you can use AWS ECR, create your own custom Registry within your cluster, or another 3rd party Docker repository)

* Deploying these Docker container(s) to a small Kubernetes cluster. For your Kubernetes cluster you can either use AWS Kubernetes as a Service, or build your own Kubernetes cluster. To deploy your Kubernetes cluster, use either Ansible or Cloudformation. Preferably, run these from within Jenkins or Circle CI as an independent pipeline.


## Setup the Environment

* Create EKS Cluster on AWS by 
    ```
    ./create_EKS.sh
    ```
* Setup Project with Circleci 

### Linting 

1. lint index.html
2. hadolint Dockerfile 
3. Build Docker image 
4. Push docker image to DockerHub 

### Apply on Kubernetes

* Apply Blue server 
* Apply Green Server when user approve 
* Get app url from cluster 
    ```
    kubectl get services --all-namespaces -o wide
    ```
