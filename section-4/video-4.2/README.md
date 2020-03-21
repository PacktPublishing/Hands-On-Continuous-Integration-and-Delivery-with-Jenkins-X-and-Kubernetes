# Video 4.2

This video demonstrates how Jenkins X uses preview environments to deploy a
temporary version of an application during a pull request.

## Prerequisites

First install your cluster per the instruction in section 1.

## Preview Environments

It is common when making changes to an application to create a "feature branch"
and make the changes in that separate branch. Once we are ready to merge the
changes into the master branch, we create a "pull request" in GitHub. This is
an opportunity for others on the team to review the changes before they are
merged into master.

Jenkins X provides additional functionality for pull requests, including running
a build of the application with the changes merged in, reporting the build
results back to the pull request review page, and deploying the application to
a temporary preview environment that reviewers can use to test the changes.

To try this out, first import the application in `hello-4-2` using `jx import`.
Then, once it has finished deploying to "staging", create a feature branch:

```
cd hello-4-2
git checkout -b trial-change
```

At this point you can edit one or more of the files. Then, commit and push the
change:

```
git add .
git commit -m 'trial change'
git push -u origin trial-change
```

If you visit the application's Git repository in GitHub, you will see Jenkins X
start building the application and report back the results. If the build is
successful, you will see it deploy to a preview environment.

## Cleanup

You can see the list of preview environments using `jx get preview` and delete
preview requirements when they are no longer needed using `jx delete preview`.
