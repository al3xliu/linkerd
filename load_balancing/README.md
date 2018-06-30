# Linkerd Load Balacing

You can define a load balancer in `dtab` section.

for example:

```yaml
admin:
  ip: 0.0.0.0
  port: 9990

routers:
- protocol: http
  # dtab control the route logic
  # in docker you have to specific the host ip address.
  dtab: /svc => /$/inet/192.168.15.119/9081
  servers:
  - ip: 0.0.0.0
    port: 8080
```

the configuration in `http proxy` section.

just modify dtab line from `/svc => /$/inet/192.168.15.119/9081` to `1 * /svc => /$/inet/192.168.15.119/9081 & 2 * /svc => /$/inet/192.168.15.120/9081`

Its very convinient, right?
