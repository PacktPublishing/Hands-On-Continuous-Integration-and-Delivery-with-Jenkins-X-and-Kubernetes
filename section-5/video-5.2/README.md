# Video 5.2

This video shows Kubernetes deployments and pods.

## Prerequisites

First install your cluster per the instruction in section 1.

## Deployments and Pods

A pod is a logical group of containers that all run on the same Kubernetes node
and share a Pod IP address. Kubernetes uses deployments to manage pods,
including creating pods, creating multiple replicas of pods, performing a
rolling update to allow for upgrading an application with zero downtime, and
replacing pods when there is a failure in a container or in a Kubernetes node.

When we create a deployment, we give it a template for the pods it creates.
This includes information on what containers to create. It also includes a
set of labels that are used by the deployment to find and manage its pods.
This means we have to configure a "selector" in the deployment that matches
the "labels" that we give in the pod template.

## Creating a Deployment

As before, we use `kubectl apply`:

```
kubectl apply -f deployment.yaml
```

We can verify that the deployment exists and that the matching pods were
created:

```
kubectl get deployment plone
kubectl get pods -l app=plone
```

## Cleaning Up

To clean up the resources in a file, we can just run `kubectl delete`:

```
kubectl delete -f deployment.yaml
```

We can also delete individual resources directly:

```
kubectl delete deployment plone
```

However, note that if you only delete a pod, the deployment will automatically
create a replacement.
