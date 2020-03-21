# Video 5.1

This video demonstrates an application deployed to Kubernetes.

## Prerequisites

First install your cluster per the instruction in section 1.

Second, you need to know the domain name that your cluster is using for
ingress. Because of the way we create the cluster using Google Kubernetes
Engine in section 1, it gets a single IP address. We can use `nip.io` to
treat that IP address as a domain, but first we need to know what it is.

To find out, run:

```
kubectl get ingress
```

You will see a list of Kubernetes Ingress resources (more on those later)
that all share the same IP address. Copy that IP address to the clipboard and
paste it into the `plone.yaml` file where it says `REPLACE_ME_INGRESS_IP`.

When finished, you should have a line in your `plone.yaml` that looks like
this (but with a different IP address; don't use this one!):

```
  - host: plone.10.11.12.13.nip.io
```

## Kubernetes

Jenkins X uses Kubernetes as the platform on which it runs its own components,
runs builds, and deploys applications. Kubernetes is a "container orchestration"
platform. This means that it runs containerized applications (such as Docker
images), providing them with configuration, storage, networking, and fault
tolerance (including health checks, load balancing, and failover).

When we deployed our cluster in Section 1, before we could run `jx boot`, we
first had to create a Kubernetes cluster on which to deploy Jenkins X. In
addition to using this cluster with Jenkins X, we can also configure it directly
using the `kubectl` command (which we saw in Section 2).

## Deploying to Kubernetes

To deploy an application to Kubernetes, we create "resources" in the cluster.
The Kubernetes control plane (the set of services that manage the cluster)
does the necessary work to start containers, configure networking, etc.

We specify the necessary resources using YAML configuration files. We can
then apply these resources to the cluster (create or update, as needed)
using the `kubectl apply` command. For example:

```
kubectl apply -f plone.yaml
```

You can now visit your Plone instance in a browser using the host name you
configured in the ingress above.

## Cleaning Up

To clean up the resources in a file, we can just run `kubectl delete`:

```
kubectl delete -f plone.yaml
```
