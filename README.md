# WordPress on a Kubernetes Structure

## Before you begin

* You need to have a Kubernetes cluster, and the kubectl command-line tool must be configured to communicate with your cluster. 

* You need a MySQL cloud solution configured and accessible.

> This project is not intented for non accustomed users with cloud solutions because we will not abord some techinal aspects, we assume you know configure your cloud and you have a litle knowlogment about kubernetes

## An overview About this project
* Docker images
  * https://hub.docker.com/r/k4izen/nginx
  * https://hub.docker.com/r/k4izen/php
* Configurations files:
  * secret keys are in @kubernetes/keys/secrets-example.yaml
  * kubernetes main yaml are in @kubernetes/wordpress.yaml
  * WordPress are in  @wordpress

>Attention! if you change the namespace from yaml's you will need to change at https://github.com/k4izen/nginx/blob/master/nginx/conf.d/upstream.conf on line 4,8 and at https://github.com/k4izen/wordpress-kubernetes-infrastructure/blob/master/wordpress/config/application.php on line 37

### Steps to mount your own structure based on this project
* rename the file kubernetes/keys/secrets-example.yaml to kubernetes/keys/secrets.yaml and edit it with your variables and site name.

```sh
kubectl create -f kubernetes/keys/secrets.yaml 
```

![Succ01](kubernetes/images/keys.png)

to check if this part is working you run this commands and see the configuration
```sh
kubectl get configmap  --namespace=wpk8s
kubectl describe configmap  --namespace=wpk8s
kubectl describe configmap wordpress-kubernetes-infrastructure  --namespace=wpk8s
kubectl describe secrets wordpress-mysql-user-password  --namespace=wpk8s
```
