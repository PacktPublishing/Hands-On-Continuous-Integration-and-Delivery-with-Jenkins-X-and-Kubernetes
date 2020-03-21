# Video 2.2

This video demonstrates importing existing code as an application in Jenkins X.

## Prerequisites

To try out this example for yourself, you will need a Jenkins X cluster up
and running. You can accomplish this by following the instructions in the
rest of Section 1.

## Import

The `jx import` command will import existing code into Jenkins X. It will
create the necessary Docker build and Helm chart to deploy the application
to Kubernetes.

This folder contains a "Hello World" Node application using Express. To import
it to Jenkins X, run:

```
jx import express-hello
```

Once the process is complete, you will have a new Git repository published to
GitHub and configured to build and deploy using Jenkins X and Kubernetes.

## Inspection

You can inspect your new application using a variety of Jenkins X commands,
as documented here:

https://jenkins-x.io/docs/using-jx/developing/browsing/
