# WordPress on a Kubernetes Structure

## Before you begin

* You need to have a Kubernetes cluster, and the kubectl command-line tool must be configured to communicate with your cluster. 

* You need a MySQL cloud solution configured and accessible.

> This project is not intented for non accustomed users with cloud solutions because we will not abord some techinal aspects, we assume you know configure your cloud and you have a litle knowlogment about kubernetes

*An overview About this project*
* Docker images
  * https://cloud.docker.com/u/k4izen/repository/docker/k4izen/nginx
  * https://cloud.docker.com/u/k4izen/repository/docker/k4izen/php
* Configurations files:
  * secret keys are in @kubernetes/keys/secrets-example.yaml
  * kubernetes main yaml are in @kubernetes/wordpress.yaml
  * WordPress are in  @wordpress
