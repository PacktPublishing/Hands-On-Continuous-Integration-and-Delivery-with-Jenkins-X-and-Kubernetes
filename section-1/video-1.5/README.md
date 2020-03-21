# Video 1.5

## GitOps

Jenkins X uses GitOps to manage the Jenkins X installation. This means
that the Jenkins X configuration is stored in a Git repository, and any
changes we make, whether directly or with the `jx` command line tool, are
reflected in the Git repository for the installation.

## GitHub Setup

In order for Jenkins X to perform GitOps, it needs access to a Git repository
server. For this course, we are using GitHub. You can choose to either use
your personal GitHub account for everything, or create a separate "bot" account
and a GitHub organization. Just be sure to follow the GitHub terms of service
for any accounts created for machine purposes.

For this video, we'll demonstrate a GitHub organization that includes a
personal account and a separate bot account. This will allow us to use the
bot account for Jenkins X changes so we can see automated changes more easily.

## GitHub Access Token

To get started, we need to give Jenkins X rights to make changes in our Git
repositories. For GitHub, we can do this by creating a personal access token.

To configure a personal access token, go here:

https://github.com/settings/tokens

Be sure that you're logged in with the account you want Jenkins X to use.

Jenkins X requires the following permissions:

* repo (all)
* read:org
* write:repo_hook
* read:repo_hook
* read:user
* user:email
* delete_repo

Once you have created a token with these permissions, be sure to keep the
token in a safe place so we can use it for `jx boot`.
