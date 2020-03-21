# Video 6.2

This video demonstrates Jenkins X addons.

## Prerequisites

First install your cluster per the instruction in section 1.

## Jenkins X Addons

Jenkins X Addons are, confusingly, different from Jenkins X Apps. There is a
proposal to merge the two concepts but for now they are separate.

A Jenkins X Addon allows us to add optional core functionality to Jenkins X.
There are a number of addons; you can run `jx create addon --help` to see a
list.

Unlike apps, addons are not tracked using GitOps.

## Installing an Addon

Run the `jx create addon` command. For example:

```
jx create addon anchore
```

## Cleaning Up

To delete the addon, run:

```
jx delete addon anchore
```
