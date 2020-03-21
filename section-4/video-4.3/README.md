# Video 4.3

This video demonstrates how to use a Jenkins X DevPod to run an application
within the Kubernetes cluster, allowing us to see changes immediately.

## Prerequisites

First install your cluster per the instruction in section 1.

## DevPod

A Jenkins X DevPod is a version of our application that is based on our local
code directories rather than what is in Git. Using a Jenkins X DevPod allows
us to test our code in a more realistic environment running in Kubernetes
itself rather than just on the local computer.

To create a DevPod, run this command from inside the code directory for an
application:

```
jx create devpod
```

This will create the DevPod and open a shell. You can then start the
application as normal (e.g. `npm start` for our example JavaScript application).

You can open an additional shell in the DevPod from another terminal window
by running:

```
jx create devpod --reuse
```

When finished, just run `jx delete devpod` to clean up.
