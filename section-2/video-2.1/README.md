# Video 2.1

This video demonstrates adding an application to Jenkins X from a quickstart.

## Prerequisites

To try out this example for yourself, you will need a Jenkins X cluster up
and running. You can accomplish this by following the instructions in the
rest of Section 1.

## Quickstart

Jenkins X includes "quickstarts", which are repositories that already have
some code available. You can use these to quickly add a new application to
Jenkins X, allowing you to place your own code into a repository that is
already configured for Jenkins X.

To create a new Jenkins X quickstart, run:

```
jx create quickstart
```

Once the process is complete, you will have a new Git repository published to
GitHub and configured to build and deploy using Jenkins X and Kubernetes.

## Inspection

You can inspect your new application using a variety of Jenkins X commands,
as documented here:

https://jenkins-x.io/docs/using-jx/developing/browsing/
