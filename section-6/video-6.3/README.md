# Video 6.3

This video demonstrates installing Prometheus as a Jenkins X addon.

## Prerequisites

First install your cluster per the instruction in section 1.

## Prometheus

Prometheus is a monitoring service. It is configured with a list of endpoints
that it "scrapes" periodically to collect data. This data can include health
information or metrics such as number of requests. Prometheus provides a
database of all of the data it scrapes for use in visualizations.

Many of the Kubernetes and Jenkins X services are already configured with
endpoints to provide data to Prometheus, and when we install Prometheus in
Kubernetes, it can automatically detect where to scrape metrics data. This
makes it very easy to add monitoring for Kubernetes components and our own
applications.

## Installing Prometheus

Install Prometheus as a Jenkins X addon:

```
jx create addon prometheus
```

Then visit the Prometheus server in the browser. You can get the URL by
running `kubectl get ingress`. Use `admin` as the username and password.

## Cleaning Up

To delete the addon, run:

```
jx delete addon prometheus
```
