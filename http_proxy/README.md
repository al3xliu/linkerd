# Linkerd as a Http proxy

## Setup app

Start your app, my application is running on 9081 port.

## Start container

./start.sh

## Test

```sh
export http_proxy=http://127.0.0.1:8080
curl -s http://api/

# your will see the output written by your service.
```
