# Video 1.6

We're now ready to install Jenkins X using the `jx boot` command.
We'll be using our Kubernetes cluster configuration and our GitHub token.

## Prerequisites

* Create a Kubernetes cluster and GitHub token per the instructions.
* Have your Git command line client installed and configured with your
  name and email.

## Jenkins X Boot

The `jx boot` command uses the cluster's Git repository to configure the
running installation of Jenkins X. This includes installing or modifying
any pieces as necessary.

When we first run `jx boot`, we will not have a Git repository, so `jx boot`
will clone it for us. It will then push this repository to the GitHub
account or organization we specify. From that point forward, we should make
configuration changes to our cluster only from within the Git repository.

To get the Jenkins X Boot process started, we can supply a
`jx-requirements.yaml` file. There is a sample one in this directory.

To run using the provided configuration:

```
jx boot -r jx-requirements.yaml
```

Once you've successfully booted Jenkins X, you can either re-clone the Git
repository it created for you, or just move the `jenkins-x-boot-config`
directory somewhere else on your system. Be sure to use this directory to
configure your cluster!

## Public vs. Private Environments

Most of `jx-requirements.yaml` matches the default, but there is one change.

Because we install into a GitHub organization that is running under the free
tier, we are only allowed to create public repositories. Jenkins X defaults
to using private repositories for cluster configuration, so we need to tell
Jenkins X to make the repositories public. We do this by setting
`environmentGitPublic` to `true` in `jx-requirements.yaml`.

If you are installing into a paid organization or a personal account, you
can choose to remove this configuration entry to use private repositories.

## Configuring TLS

This Jenkins X setup is designed for you to learn how to use Jenkins X.
Once you have your Jenkins X cluster up and running, you will want to
configure Transport Layer Security (TLS). To enable TLS, you will need a custom
domain that you own in order to issue the certificates. For this reason,
enabling TLS is not shown as part of the course.

It's important to enable TLS, because our Jenkins X server will be creating
webhooks to GitHub that include tokens that Jenkins X uses to ensure that the
webhook comes from the right source. We want to secure the communication from
GitHub to Jenkins X to ensure that token is not sent in the clear. To do this we
need to enable TLS in `jx-requirements.yaml`.
