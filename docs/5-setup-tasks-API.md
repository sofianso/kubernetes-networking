# Purpose
Set-up TASKS API.

## Docker Repo
After you configured kubernetes files for both deployment and service, you need to create and push into your Docker repo.
Build the image:
`docker build -t sofianso/kube-demo-tasks`
Push the image:
`docker push sofianso/kube-demo-tasks`

## Apply Kubernetes Settings
`kubectl apply -f=tasks-deployment.yaml -f=tasks-service.yaml`

Check if deployment was successful:
`kubectl get deployments`

Check if pod was successful:
`kubectl get pods`

## Running Tasks Service
Run the following command to obtain the URL in which you can POST/GET tasks using POSTMAN.
`minikube service tasks-service`

## Setting Up Postman
Before you GET/POST any requests to TASKS

You must set the `Authorization` in `Headers` to the value set in AUTH API to `Bearer abc` as shown below.
![Postman Header](images/postman-header.png)
