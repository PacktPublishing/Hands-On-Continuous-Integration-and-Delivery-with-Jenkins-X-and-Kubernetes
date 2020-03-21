# Video 3.2

This video demonstrates how Jenkins X can auto-detect the build pack and how
it can be specified on the command line.

## Prerequisites

First install your cluster per the instruction in section 1.

## Build Pack Auto-detection

When we run `jx import`, Jenkins X looks for a `jenkins-x.yml` file. If it
is not present, it will attempt to auto-detect the build pack to use based
on what type of code it finds in the directory.

To see an example of auto-detection, import the `hello-3-2-auto` folder.

```
jx import hello-3-2-auto
```

Once the project is imported, you can see a new file `jenkins-x.yml` with
the content:

```
buildPack: javascript
```

## Specify Build Pack

We can specify the build pack either by creating the `jenkins-x.yml` file or
by specifying on the command line.

To see the list of available build packs:

```
jx import --list-packs
```

To specify a build pack (using `hello-3-2-specify` as an example):

```
jx import hello-3-2-specify --pack=javascript
```
