# Video 6.1

This video demonstrates adding "apps" to Jenkins X.

## Prerequisites

First install your cluster per the instruction in section 1.

Second, if you installed Helm 3 in your PATH as part of Video 5.5, you may
need to make sure it is no longer in your PATH, as of this writing (March 2020)
Jenkins X does not yet support Helm 3.

## Jenkins X Apps

Jenkins X has the concept of an "app" that we can add to the cluster. This is
different from an application that Jenkins X builds and deploys; Jenkins X
only manages deployement for an app.

We can deploy an app using a Helm chart; the only difference with using Helm
directly is that Jenkins X will manage the deployment for us using GitOps
so we can more easily rebuild the cluster if needed.

## Adding an App to Jenkins X

We can add an app to Jenkins X by referencing the name and repository for the
Helm chart. For example:

```
jx add app mongodb --repository https://charts.bitnami.com/bitnami
```

This will create a pull request that will eventually end up adding MongoDB
to our Kubernetes cluster.

## Cleaning Up

To delete the MongoDB Jenkins X app, run:

```
jx delete app mongodb
```
