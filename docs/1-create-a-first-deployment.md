## Create a Docker Repo

For this example:
https://hub.docker.com/repository/docker/sofianso/kube-demo-users

## Build the image

NOTE: Don't forget to go into `users-api` directory.
Build the image using the same Docker repo name.

`docker build -t sofianso/kube-demo-users .`

## Push the image

`docker push sofianso/kube-demo-users`

## Apply Deployment and Service Config

NOTE: Don't forget to go into `kubernetes` directory.
`kubectl apply -f=users-deployment.yaml`

`kubectl apply -f=users-service.yaml`

## Running Service File

Copy the URL created by minikube and use it to GET/POST data.
`minikube service users-service.yaml`
