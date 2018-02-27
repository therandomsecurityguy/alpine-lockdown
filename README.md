# alpine-lockdown

Hardened Alpine Linux image, run with an unprivileged user.

## About the Container

[Alpine Linux](https://alpinelinux.org/) is used as a base image, which is a lightweight distribution with a small surface area for security concerns. It has enough functionality for development and interactive debugging.

To prevent zombie reaping processes, we use [dumb-init](https://github.com/Yelp/dumb-init) as PID 1 which forwards signals to all processes running in the container.


## Configuration Parameter

_These Settings are **optional**, if not set the default values will be used._

```
# Optional Configuration Parameter
ARG SERVICE_USER  # Username
ARG SERVICE_HOME  # User Home Directory

# Default Settings
ENV SERVICE_USER ${SERVICE_USER:-app}
ENV SERVICE_HOME ${SERVICE_HOME:-/home/${SERVICE_USER}}
```

Documentation: <https://docs.docker.com/compose/compose-file/#/args>
