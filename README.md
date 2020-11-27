## Helm

Micro can be installed onto a Kubernetes cluster using helm. Micro will be deployed in full and leverage zero-dep implementations designed for Kubernetes. For example, micro store will internally leverage a file store on a persistant volume, meaning there are no infrastructure dependancies required.

### Dependencies

You will need to be connected to a Kubernetes cluster

### Install

Install micro with the following commands:

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

## Artifac tHub

Micro is available via [Artifact Hub](https://artifacthub.io/packages/helm/micro/micro)
