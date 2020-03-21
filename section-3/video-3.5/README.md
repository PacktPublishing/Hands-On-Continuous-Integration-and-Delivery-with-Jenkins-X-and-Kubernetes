# Video 3.5

This video demonstrates how to add or replace build steps in a Jenkins X
build pack.

## Prerequisites

First install your cluster per the instruction in section 1.

## Build Pack Overrides

We can add or replace build steps in a pipeline through the `jenkins-x.yml`
file.

For example, to add `npm audit` to our JavaScript build, we just need this
content in `jenkins-x.yml`:

```
buildPack: javascript
pipelineConfig:
  pipelines:
    release:
      build:
        steps:
        - sh: npm audit
          name: npm-audit
```

This will result in `npm audit` being run after all of the build steps that
are defined in the build pack (including any build steps in inherited
pipelines).

If we instead want to completely replace the build steps, we can use the
`replace` field. For example, to change the JavaScript build to remove the
`npm test` step:

```
buildPack: javascript
pipelineConfig:
  pipelines:
    release:
      build:
        replace: true
        steps:
        - sh: jx step credential -s npm-token -k file -f /builder/home/.npmrc --optional=true
          name: npmrc
        - sh: npm install
          name: npm-install
        - sh: export VERSION=$PREVIEW_VERSION && skaffold build -f skaffold.yaml
          name: container-build
```

Note that we needed to bring in the build steps from all of the inherited
pipeline files because they are all replaced.
