# Purpose

To allow `auth-api` to connect to `users-api` in the same Kubernetes pod.

## Build The Auth Image & Users API

You should build the auth and users image after you change the environment settings.
`docker build -t sofianso/kube-demo-auth .`

`docker build -t sofianso/kube-demo-users .`

## Push The Auth Image

After the image is built, you push the local image to Docker hub.
`docker push sofianso/kube-demo-auth`

## Add the image to Kubernetes deployment pod

Don't forget to pull the latest image by adding `:latest`.

```
- name: auth
  image: sofianso/kube-demo-auth:latest
```

## Making sure the AUTH API is unreachable from CLIENT

To clarify, USERS API needs to be reachable from outside the pod.
In this case, we will use `localhost` which would be configured in Kubernetes deployment yaml file.

```
env:
    - env: AUTH_ADDRESS
    value: localhost

```

Next is to update the new Kubernetes deployment yaml file.
`kubectl apply -f=users-deployment.yaml`
