# Purpose

To set-up `nginx.conf` to GET/POST tasks which will remove hardcoding the URL in `frontend` app.

## Configure nginx.conf file

Add the following block of code that will allow the `/api` path to be redirected to the `proxy_pass` URL.

PORT `8000` is port/targetPort of Tasks API.

```
location /api {
proxy_pass http://tasks-service.default:8000/;
}
```

Next step is to edit the `frontend` to fetch and post tasks by using the `/api` path assigned in `nginx.conf`.

