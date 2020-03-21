# Video 5.3

This video shows Kubernetes services.

## Prerequisites

First install your cluster per the instruction in section 1.

## Services

Pods may come and go in a cluster, either because of failure or because we
are upgrading our application. In addition, we may have multiple pod replicas
to providing horizontal scaling. Therefore, while each pod has its own IP
address, we can't use the pod IP address to reliably communicate with our
application.

A Kubernetes service provides a well-known name and a long-lasting IP address
for our application. The service receives a cluster IP address, and any traffic
to the cluster IP address is automatically load balanced across all pods that
match the service's selector. Even as pods come and go, clients can still use
the service and will be routed to a healthy pod.

## Creating a Service

As before, we use `kubectl apply`:

```
kubectl apply -f service.yaml
```

We can verify that the service exists and matches the pods in the deployment:

```
kubectl get service plone
kubectl describe service plone
```

## Cleaning Up

To clean up the resources in a file, we can just run `kubectl delete`:

```
kubectl delete -f service.yaml
```

We can also delete individual resources directly:

```
kubectl delete service plone
kubectl delete deployment plone
```
