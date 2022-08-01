# Purpose
Deploy `frontend` app to Kubernetes pod inside the same cluster.

## Docker Repo
Remember to create the repo on your Docker hub repo first.
Push the Docker image using:

`docker push sofianso/kube-demo-frontend`

## Applying FRONTEND Service & Deployment
`kubectl apply -f=frontend-deployment.yaml -f=frontend-service.yaml`

## Get FRONTEND URL from Kubernetes Service
`kubectl service frontend-service`
