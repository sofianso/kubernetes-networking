# Purpose
To create a simple frontend app that will allow users to GET/POST tasks (instead of using POSTMAN).

This will require the additional CORS config to be passed to TASKS API.

## Build The Dockerfile
NOTE: Make sure you are in the right directory
`docker build -t sofianso/kube-demo-frontend .`

## Run Docker Image
`docker run -p 80:80 -rm -d sofianso/kube-demo-frontend`

## Redeploy Tasks API
After modifying TASKS API with the CORS config, you need to redeploy the app again.

`docker push sofianso/kube-demo-tasks`

NOTE: You MUST delete the deployment pod from Kubernetes before reapplying it again:
`kubectl delete -f=tasks-deployment.yaml`

Reapply the settings by running:
`kubectl apply -f=tasks-deployment.yaml`

Adding HEADERS to fetchTasks (in frontend) is needed to allow the `frontend` app to communicate to the TASKS API.
```
headers: {
'Authorization': 'Bearer abc',
},
```