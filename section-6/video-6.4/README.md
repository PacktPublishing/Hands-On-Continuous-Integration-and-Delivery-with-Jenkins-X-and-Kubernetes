# Video 6.4

This video demonstrates installing Grafana as a Jenkins X addon.

## Prerequisites

First install your cluster per the instruction in section 1.

## Grafana

Grafana is a visualization tool. It can pull data from sources such as
Prometheus and present them in a variety of ways.

## Installing Grafana

Install Grafana as a Jenkins X addon:

```
jx create addon grafana
```

Next, we need to retrieve the password. First get the name of the running
pod:

```
kubectl get pods -l app=grafana
```

Now use that pod name to get the password:

```
kubectl exec -ti <pod name> env | grep PASS
```

## Cleaning Up

To delete the addon, run:

```
jx delete addon grafana
```
