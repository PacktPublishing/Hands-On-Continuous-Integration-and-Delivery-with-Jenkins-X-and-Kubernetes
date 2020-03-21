# Video 2.6

This video demonstrates the underlying Kubernetes resources that Jenkins X
creates when it deploys an application.

## Prerequisites

To see the Kubernetes resources for applications in your own cluster, create
your Jenkins X installation as described in Section 1, then add at least one
application as described in Video 2.1 or 2.2.

## Kubernetes

Kubernetes is a container orchestration platform. Jenkins X uses Kubernetes to
run its own components, run builds, and deploy applications. We can use the
`kubectl` command to inspect Kubernetes resources.

Kubernetes organizes containers and other resources into namespaces. We can
see the list of namespaces using:

```
kubectl get ns
```

Kubernetes organizes running containers into "pods". To see the pods in the
`jx-staging` namespace, we can run:

```
kubectl -n jx-staging get pods
```

Finally, we can see the log for a given pod using:

```
kubectl -n jx-staging logs <pod name>
```

See the video for examples.
