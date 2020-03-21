# Hands-On Continuous Integration and Delivery with Jenkins X and Kubernetes

This code repository contains examples from the video course Hands-On
Continuous Integration and Delivery with Jenkins X and Kubernetes by Alan Hohn,
published by Packt Publishing.

## Layout

This repository is laid out based on the course videos. The first video after
the course introduction includes a complete demo, so the `section-1/video-1.2`
folder contains an application you can deploy to Jenkins X.

## Prerequisites

Jenkins X currently supports for Google Kubernetes Engine, so you will need
a Google Cloud account.

## Getting Started

After the demo in Video 1.2, the rest of Section 1 provides the instructions
for creating your Jenkins X cluster on Google Kubernetes Engine and linking
it to GitHub.

## Important Note

We will be using cloud resources, with the possibility that this will cost
money. Google Cloud Platform has a limited-time free tier, and our
setup will stay within the free tier, but once your free period expires
there will be a cost, which is greater as long as you have nodes in your
cluster's node pool.

To reduce costs while keeping your cluster configuration, you can resize the
cluster's node pool to 0, and then size it back up when you're ready to use
it. Remember to also turn off autoscaling so it doesn't scale back up again,
and revisit the cluster page to make sure the nodes were deleted properly.

Of course, you can also delete your cluster entirely and re-create it using
the instructions in Section 1.

## Application Cleanup

Throughout these videos, we will be creating applications in our Jenkins X
cluster. These applications will continue to run unless deleted or the cluster
is deleted from Google Kubernetes Engine.

To delete applications from Jenkins X, use the `jx delete application`
command. This will prompt you for one or more applications to delete. You will
have to manually remove the Git repository in GitHub.

One note of caution: as of when these videos were recorded, deleting the
application does not completely remove it from Jenkins X. There will still be
files in the boot configuration repository and Helm charts in chartmuseum. For
this reason, it is not safe to delete an application and add a new application
with the same name.
