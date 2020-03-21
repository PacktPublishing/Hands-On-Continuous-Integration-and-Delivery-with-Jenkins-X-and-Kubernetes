# Video 3.1

This video demonstrates how Jenkins X uses build packs to tell it what
steps to take to build, test, and deploy software.

## Prerequisites

To see the Jenkins X build packs, configuration file, and resulting build
steps in your own cluster, first install your cluster per the instructions
in section 1.

## Build Packs

Jenkins X includes "build packs", which contain instructions for how to build
and deploy code in various programming languages (Java, Python, JavaScript,
etc.).

Default Jenkins X build packs are in Git repositories on GitHub. Jenkins X
downloads build packs to our `$HOME/.jx` directory so it can choose the right
build pack for our code.

To get started, import the JavaScript project in this folder:

```
jx import hello-video-3-1
```

Once the project is imported, you can see a new file `jenkins-x.yml` with
the content:

```
buildPack: javascript
```

This tells Jenkins X what build pack to use to build the project.
