## Micro Helm Chart

Micro is an open source platform for API backend development, cloud native applications and microservices.

## Overview

Micro can be installed onto a Kubernetes cluster using helm. Micro will be deployed in full and leverage zero-dep implementations 
designed for Kubernetes. For example, the Micro Store service will internally leverage a file store on a persistent volume, meaning 
there are no infrastructure dependencies required.

<img src="https://micro.mu/images/micro-3.0.png" />

## Dependencies

You will need to be connected to a Kubernetes cluster

## Usage

### Install

Install Micro on Kubernetes using helm with the following commands:

```shell
helm repo add micro https://micro.github.io/helm
helm install micro micro/micro
```

### Uninstall

Uninstall micro with the following commands:

```shell
helm uninstall micro
helm repo remove micro
```

### Connect

Micro exposes a HTTP API on port 8080 and a gRPC proxy on port 8081 for remote access.

By port forwarding we'll make our "local" env micro running on kubernetes.

### Install CLI
Download and install the binary locally for the CLI

```
# MacOS
curl -fsSL https://raw.githubusercontent.com/micro/micro/master/scripts/install.sh | /bin/bash

# Linux
wget -q  https://raw.githubusercontent.com/micro/micro/master/scripts/install.sh -O - | /bin/bash

# Windows
powershell -Command "iwr -useb https://raw.githubusercontent.com/micro/micro/master/scripts/install.ps1 | iex"
```

### Port Forward

```
# port forward to the proxy
kubectl port-forward svc/proxy -n micro 8081:443

# list services
micro services

# port forward to the api
kubectl port-forward svc/api -n micro 8080:443

# curl to config api usage
curl -I http://localhost:8080/registry/ListServices
```


## Community

Come join the [Slack](https://slack.micro.mu) to learn more or follow us on [Twitter](https://twitter.com/microhq)

## Source

Check out [Github](https://github.com/micro/micro) for the source

