# Video 4.4

This video demonstrates editing an application in a DevPod using the editor
built into the DevPod.

## Prerequisites

First install your cluster per the instruction in section 1.

## DevPod

Jenkins X can provide an editor running within the DevPod; by default this is
Visual Studio Code. We can use this to edit our application source code from
a web browser to rapidly see changes.

Start by creating a DevPod:

```
jx create devpod
```

From the DevPod shell, note the URL for the IDE. Also start the application.

At this point you can visit the IDE in the browser to edit your code.
