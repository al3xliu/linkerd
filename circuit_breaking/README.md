#!/bin/bash

set -e

docker run -d \
--name "linkerd" \
-p 8080:8080 \
-p 9990:9990 \
-v `pwd`/linkerd.yaml:/linkerd.yaml \
buoyantio/linkerd:1.4.2 /linkerd.yaml
