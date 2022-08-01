# Purpose
Creating auto-generated domain names using CoreDNS which we will use for USERS API.

## Modify Environment Value
You must modify the value of the environment to use `auth-service.default`. If the namespace isn't assigned then we use `default`.

`auth-service.default` = `name_of_service.namespace`

Get namespaces: 

`kubectl get namespaces`


