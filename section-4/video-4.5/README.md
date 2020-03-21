# Video 4.5

This video shows how Jenkins X uses Skaffold to build the Docker images used
to run applications.

## Prerequisites

None

## Skaffold

Skaffold is a tool to help with the building of Docker images. It allows us
to configure the Docker build using a YAML file rather than passing all of
the parameters on the command line to `docker build`. It also supports
incremental re-build, so it can be used for rapid development.

When we import a project, Jenkins X creates a `Dockerfile` and `skaffold.yaml`
file if they don't already exist. The `Dockerfile` consists of instructions to
Docker as to how to build the image. The `skaffold.yaml` configures the name of
the image, what registry to push to after completion, and other parameters.

The `Dockerfile` and `skaffold.yaml` come from the build pack so they can be
specific to the language and runtime we're using (e.g. `javascript` with Node).
The build pack also contains the command to run `skaffold` to build and push
the image.
