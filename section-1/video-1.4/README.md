# Video 1.4

To create a Kubernetes cluster for Jenkins X, we will use Google Kubernetes
Engine.

## Prerequisites

In order to complete this lesson, you will need to create an account with
Google Cloud Platform:

https://cloud.google.com/

You will also need a Google Cloud Platform project. Follow the instructions
here:

https://cloud.google.com/resource-manager/docs/creating-managing-projects

Finally, you will need the `jx` command line tool as installed in the previous
video.

## Creating a Cluster

We will use the `jx create cluster gke` command to create the cluster.

Run:

```
jx create cluster gke --cluster-name=jenkinsx --skip-installation
```

Follow the prompts as described in the video.
