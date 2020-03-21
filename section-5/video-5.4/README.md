# Video 5.4

This video shows Kubernetes ingress resources.

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

You will see a list of Kubernetes Ingress resources (as described in this video)
that all share the same IP address. Copy that IP address to the clipboard and
paste it into the `plone.yaml` file where it says `REPLACE_ME_INGRESS_IP`.

When finished, you should have a line in your `plone.yaml` that looks like
this (but with a different IP address; don't use this one!):

```
  - host: plone.10.11.12.13.nip.io
```

## Ingress

The cluster IP we created for our service is only accessible from inside the
cluster. While there are other types of services that we can use to get
external IP addresses (IP addresses that we can access from outside the cluster)
it is usually easier and more efficient to just use an ingress.

An ingress is a special kind of Kubernetes service that has an external IP
address and routes traffic to services. The ingress has an ingress controller
that is configured with rules telling it how to route traffic. This typically
means HTTP traffic, and the rules are based on the `Host` header in the request
or matching the path of the URL.

The ingress uses these rules to route traffic to a service; the service then
routes traffic to a specific pod instance.

## Creating an Ingress

As before, we use `kubectl apply`:

```
kubectl apply -f plone.yaml
```

We can verify that the ingress exists and has the right routing rules:

```
kubectl get ingress plone
kubectl describe ingress plone
```

## Cleaning Up

To clean up the resources in a file, we can just run `kubectl delete`:

```
kubectl delete -f plone.yaml
```

We can also delete individual resources directly:

```
kubectl delete ingress plone
kubectl delete service plone
kubectl delete deployment plone
```
