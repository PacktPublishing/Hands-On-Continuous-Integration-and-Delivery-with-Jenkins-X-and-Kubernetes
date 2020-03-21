# Video 5.5

This video demonstrates Helm, the Kubernetes package manager.

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

You will see a list of Kubernetes Ingress resources (as described previously)
that all share the same IP address. Copy that IP address to the clipboard and
paste it into the `values.yaml` file where it says `REPLACE_ME_INGRESS_IP`.

When finished, you should have a section in your `values.yaml` that looks like
this (but with a different IP address; don't use this one!):

```
hosts:
  - bookstack.10.11.12.13.nip.io
```

Finally, you need to install the Helm client and add the stable repo as
described [in the documentation][helm].

[helm]:https://helm.sh/docs/intro/quickstart/

## Helm

To deploy an application to Kubernetes, we need to know not just about
Kubernetes but also about how to configure the application we're deploying.
Additionally, Kubernetes YAML files quickly get long and hard to maintain.

Helm is designed to address this by offering "charts", which are collections
of Kubernetes resources designed to make it easy to deploy an application.
Helm supports downloading and installing charts from repositories, overriding
configuration for a chart, upgrading a chart to a new version, and deleting
a chart.

Once Helm is configured, you can install an application from a chart using:

```
helm install bookstack stable/bookstack -f values.yaml
```

The application will take a few minutes to install and be available. You can
verify it by visiting the URL in the browser.

## Cleaning Up

To delete the application:

```
helm delete bookstack
```
