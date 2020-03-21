# Video 5.6

This video demonstrates debugging applications within Kubernetes.

## Prerequisites

First install your cluster per the instruction in section 1.

## Debugging Kubernetes

Once an application is up and running, Kubernetes will do its best to keep
it running with the number of specified replicas, and will route traffic
to it. However, sometimes it can be challenging to get an application up
as it can be challenging to figure out what is going wrong.

There are a few key commands for debugging an application in Kubernetes:

* `kubectl get <type> [<name>]`: List all resources of `type`, or just the
  resource with the provided `name`. Use an output format such as `-o wide`
  to get more information, or `-o yaml` to see the complete configuration.
* `kubectl describe <type> <name>`: Show the current status of the resource,
  together with recent events.
* `kubectl logs <pod name>`: See the logs for an individual pod.
* `kubectl exec -ti [-c <container>] <pod name> <command name>`: Run a command
  inside a pod. If there are multiple containers in the pod you must provide
  a container name.

Generally, the first two commands are used prior to getting the pod to the
`Running` state, and the last two commands are used after the pod runs the
first time.

There are multiple different error states for a pod, but two are the most
commonly seen:

* `ImagePullBackOff`: This means that Kubernetes has tried multiple times to
  pull the Docker image and has been unsuccessful. This may indicate that the
  image name is incorrect, that the registry is down, or that there is an
  issue with authentication or authorization to pull the image.
* `CrashLoopBackOff`: This means that Kubernetes was able to pull the image,
  but the command to start the container keeps failing. This may indicate a
  bad command, a bad configuration of the pod, or an error in the application
  that causes it to exit. If the pod is configured with health checks, it may
  also mean that the pod is failing health checks.

To help illustrate these errors, this folder has three deployments:

* `bad-image-name`: The name of the Plone image is misspelled to cause an
  `ImagePullBackOff`.
* `bad-command`: The command `/bin/false` is specified to cause a container
  that will fail repeatedly and cause `CrashLoopBackOff`.
* `good-deployment`: Both of these errors are fixed to allow creation of a
  `Running` container to test `log` and `exec`.
